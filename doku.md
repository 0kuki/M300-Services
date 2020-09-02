### 19.08
***
* Infrastructure as Code: Prinzipien der softwareentwicklung angewendet auf Systemtechnik
  * Versionsverwaltung und textbasierte config files
* Mit Vagrant können anhand von einem "vagrantfile" einfach viele VMs erstellt werden
  * Einfache ubuntu VM erstellt mit:
    ```
    Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/xenial64"
    end
    ```