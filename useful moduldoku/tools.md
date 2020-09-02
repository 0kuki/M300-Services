
## Git Bash
### Übersicht "How to Push"
***

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
