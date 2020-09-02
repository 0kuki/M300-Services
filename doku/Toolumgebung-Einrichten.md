# Toolumgebung Einrichten

## Repository Erstellen

#### Was ist ein Repository?
Ein Repository ist eine zentrale Ablage für Daten, Dokumente, Objekte und Programme. Es dient zur Speicherung von verschiedenen Versionen des Projekts und lässt mehrere Benutzer gleichzeitig an einem Projekt arbeiten.

### Erstellung des Repositories
![Repo Creation Screenshot](/doku/img/repo_creation.png "Repo Creation Screenshot")

## SSH Key erstellen

#### Was ist ein SSH-Key?
Mit SSH ist es möglich, eine sichere Verbindung zu einem Netzwerkgerät herzustellen. Mit einem SSH-Key sorgt man für die nötige Sicherheit.

#### Was ist ein SSH-Agent?
Ein SSH-Agent hält alle privaten Schlüssel dekodiert im Speicher, sobald man einmal die entsprechende Passphrase eingegeben hat. Ein ständiges Eintippen der Passphrase für jede neue SSH-Verbindung einfällt somit.

### SSH-Key erstellen
```ssh-keygen -t rsa -b 4096 -C "user.name@domain.tld"```
![SSH key Creation Screenshot](/doku/img/create_ssh_key.png "SSH key Creation Screenshot")
### Client konfigurieren
Im git client den nutzernamen und die github account email eintragen
```git config --global user.name Kejenmo```
```git config --global user.email kejenmo.mohan@gmail.com```
### Repository klonen

![repo clone Screenshot](/doku/img/clone_repo.png "repo clone Screenshot")
### Übersicht "How to Push"
***
(übernommen aus  [mc-b/M300](https://github.com/mc-b/M300/tree/master/10-Toolumgebung))

Dieser Abschnitt zeigt die Handhabung von Git-Befehlen auf. Mit den nachfolgenden Kommandos pusht man das (geänderte) Repository zu seinem GitHub-Repository.

Wichtig: Die Befehle müssen innerhalb des lokalen Repositorys ausgeführt werden!

```Shell 
$  cd Pfad/zu/meinem/Repository    # Zum lokalen GitHub-Repository wechseln

$  git status                      # Geänderte Datei(en) werden rot aufgelistet
$  git add -A                      # Fügt alle Dateien zum "Upload" hinzu
$  git status                      # Der Status ist nun grün > Dateien sind Upload-bereit (Optional) 
$  git commit -m "Mein Kommentar"  # Upload wird "commited" > Kommentar zu Dokumentationszwecken ist dafür notwendig
$  git status                      # Dateien werden nun als "zum Pushen bereit" angezeigt
$  git push                        #Upload bzw. Push wird durchgeführt
```


