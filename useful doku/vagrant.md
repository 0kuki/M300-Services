
### Virtuelle Maschine erstellen
***
1. Terminal (*Bash*) öffnen
2. In gewünschtem Verzeichnis einen neuen Ordner für die VM anlegen:
    ```Shell
      $ cd Wohin/auch/immer
      $ mkdir MeineVagrantVM
      $ cd MeineVagrantVM
    ``` 
3. Vagrantfile erzeugen, VM erstellen und entsprechend starten:
    ```Shell
      $ vagrant init ubuntu/xenial64        #Vagrantfile erzeugen
      $ vagrant up --provider virtualbox    #Virtuelle Maschine erstellen & starten
    ``` 
4. Die VM ist nun in Betrieb (erscheint auch in der Übersicht innerhalb von VirtualBox) und kann via SSH-Zugriff bedient werden:
    ```Shell
      $ cd Pfad/zu/meiner/Vagrant-VM      #Zum Verzeichnis der VM wechseln
      $ vagrant ssh                       #SSH-Verbindung zur VM aufbauen

      #Anschliessend können ganz normale Bash-Befehle abgesetzt werden:

      $ ls -l /bin  #Bin-Verzeichnis anzeigen
      $ df -h       #Freier Festplattenspeicher
      $ free -m     #Freier Arbeitsspeicher
    ``` 
5. VM über VirtualBox-GUI ausschalten

Schlussfolgerung: Eine VM lässt sich mit Vagrant eindeutig schneller und unkomplizierter erstellen!


### Apache Webserver automatisiert aufsetzen
***
Um den Automatisierungsgrad von Vagrant im Rahmen dieser Dokumentation etwas besser hervorzuheben, richten wir eine VM, dass sie direkt mit einem vorinstallierten Apache-Webserver startet. Dazu können wir im Vagrantfile den Code etwas leicht abändern und direkt auf Bash-Ebene mit einfachen Befehlen arbeiten. 

Nachfolgend wird die VM mit einem bereits abgeänderten File bzw. VM aus dem M300-Repository erstellt:

1. Terminal (*Bash*) öffnen
2. In das M300-Verzeichnis (/M300/vagrant/web) wechseln:
    ```Shell
      $ cd Pfad/zum-M300-Verzeichnis/vagrant/web
    ``` 
3. VM erstellen und starten:
    ```Shell
      $ vagrant up
    ``` 
4. Webbrowser in der VM öffnen und prüfen, ob der Standard-Content des Webservers unter "http://127.0.0.01:8080" (localhost) erreichbar ist
5. Im Ordner `/web` die Hauptseite `index.html` editieren bzw. durch eine andere ersetzen (z.B. HTML5up-Themplate) und das Resultat überprüfen
6. Abschliessend kann die VM wieder gelöscht werden:
    ```Shell
      $ vagrant destroy -f
    ```
7. Vagrant ist nun komplett einsatzfähig!


Demo Vagrantfile:

```
Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "forwarded_port", guest:80, host:8080, auto_correct: true
  config.vm.synced_folder ".", "/var/www/html"  
config.vm.provider "virtualbox" do |vb|
  vb.memory = "512"  
end
config.vm.provision "shell", inline: <<-SHELL
  # Packages vom lokalen Server holen
  # sudo sed -i -e"1i deb {{config.server}}/apt-mirror/mirror/archive.ubuntu.com/ubuntu xenial main restricted" /etc/apt/sources.list 
  sudo apt-get update
  sudo apt-get -y install apache2 
SHELL
end
```
