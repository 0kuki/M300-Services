# Doku Vagrantfiles
Speziellere Aktionen in den Vagrantfiles sind hier beschrieben. Dinge die in mehreren files vorkommen werden nur einmal beschrieben.
### 01 MeineVagrantVM - Erstes Vagrantfile

```
Vagrant.configure("2") do |config|
config.vm.box = "ubuntu/xenial64"
end
```
Nennenswertes
1. Spezifiziert die version der Vagrant config version 2
2. Nutzt eine Ubuntu x64 Vagrantbox von Hashicorp's Vagrantcloud
3. ende

### 02 vagrantWeb - Vagrantfile für Webserver
```
Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "forwarded_port", guest:80, host:8080, auto_correct: true
  config.vm.synced_folder ".", "/var/www/html"  
config.vm.provider "virtualbox" do |vb|
  vb.memory = "512"  
end
config.vm.provision "shell", inline: <<-SHELL
  sudo apt-get update
  sudo apt-get -y install apache2 
SHELL
end
```
Nennenswertes:
* Portweiterleitung von port 80 auf 8080 
* synchronisierter ordner auf hostsystem zu /var/www/html
* Virtualbox als VM provider
* 512mb RAM Zugewiesen
* Shellkommandos:
    * Update der paketlisten
    * Installation Apache webserver
### 03 Firewall - Vagrantfile für Webserver mit Firewall
```
Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "forwarded_port", guest:80, host:8080, auto_correct: true
  config.vm.synced_folder ".", "/var/www/html"  
config.vm.provider "virtualbox" do |vb|
  vb.memory = "512"  
end
config.vm.provision "shell", inline: <<-SHELL
  sudo apt-get update
  sudo apt-get -y install apache2 
  sudo ufw deny 3306
  sudo ufw allow from 192.168.0.1 to any port 22
  sudo ufw allow from 192.168.0.1 to any port 3306
  sudo ufw enable
  sudo ufw status
SHELL
end
```
Nennenswertes:
* port 3306 in ufw (ubuntu firewall) gesperrt
* 192.168.0.1 port 22 in ufw erlaubt
* 192.168.0.1 port 3306 in ufw erlaubt
* ufw aktiviert
* ufw status abgerufen (ausgabe in konsole)

### 04 FWRP - Vagrantfile für Proxy Server
ToDo

### 05 Auth - Vagrantfile für Apache mit Benutzerauthentifizierung
```
Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "forwarded_port", guest:80, host:8080, auto_correct: true
  config.vm.synced_folder ".", "/var/www/html"  
config.vm.provider "virtualbox" do |vb|
  vb.memory = "512"  
end
config.vm.provision "shell", inline: <<-SHELL
  sudo apt-get update
  sudo apt-get -y install apache2 
  sudo ufw deny 3306
  sudo ufw allow from 192.168.0.1 to any port 22
  sudo ufw allow from 192.168.0.1 to any port 3306
  sudo ufw enable
  sudo ufw status
  #Passwort
  sudo apt update
  sudo apt install apache2-utils
  vi /etc/apache2/sites-enabled/000-default.conf
  sudo nano /etc/apache2/sites-enabled/000-default.conf
  sudo nano .htaccess
  cat .htaccess
  sudo service apache2 restart
SHELL
end
```
Nennenswertes:
* installation von apache2-utils
* erstllen von /sites-enabled/000-default.conf
* erstellen von .htaccess
* restart apache2 dienst
