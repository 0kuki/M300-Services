# Docker Befehle

| Befehl | Funktion |
|--|--|
| docker run -it ubuntu /bin/bash | Startet einen Container mit einer interaktiven Shell |
| docker run -d ubuntu sleep 20 | Startet einen Container, der im Hintergrund läuft |
| docker run -d –rm ubuntu sleep 20 | Startet einen Container im Hintergrund und löscht diesen nach Beendigung des Jobs |
| docker run -d ubuntu touch /tmp/lock | Startet einen Container im Hintergrund und legt eine Datei an |
| docker run -d ubuntu ls -l | Startet einen Container im Hintergrund und gibt das ROOT-Verzeichnis nach STDOUT aus |
| docker ps | Zeigt aktive Container an |
| docker ps -a | Zeigt aktive und beendet Container |
| docker ps -a -q | Gibt die IDs aus |
| docker stopp | Stoppt einen oder mehrere Container |
| docker kill | Schickt ein Signal an den Hauptprozess in einem Container, womit der Container sofort stoppt. |
| docker logs | Gibt die Logs für einen Container aus |
| docker inspect | Gibt umfangreiche Informationen zu Container oder Images aus. |
| docker diff | Gibt die Änderungen am Dateisystem des Containers verglichen mit dem Image aus, aus dem er gestartet wurde. |
