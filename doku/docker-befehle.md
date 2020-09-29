# Docker Befehle

| Befehl | Funktion |
|--|--|
| docker run -it ubuntu /bin/bash | Startet einen Container mit einer interaktiven Shell |
| Docker run -d ubuntu sleep 20 | Startet einen Container, der im Hintergrund läuft |
| Docker run -d –rm ubuntu sleep 20 | Startet einen Container im Hintergrund und löscht diesen nach Beendigung des Jobs |
| Docker run -d ubuntu touch /tmp/lock | Startet einen Container im Hintergrund und legt eine Datei an |
| Docker run -d ubuntu ls -l | Startet einen Container im Hintergrund und gibt das ROOT-Verzeichnis nach STDOUT aus |
| Docker ps | Zeigt aktive Container an |
| Docker ps -a | Zeigt aktive und beendet Container |
| Docker ps -a -q | Gibt die IDs aus |
| Docker stopp | Stoppt einen oder mehrere Container |
| Docker kill | Schickt ein Signal an den Hauptprozess in einem Container, womit der Container sofort stoppt. |
| Docker logs | Gibt die Logs für einen Container aus |
| Docker inspect | Gibt umfangreiche Informationen zu Container oder Images aus. |
| Docker diff | Gibt die Änderungen am Dateisystem des Containers verglichen mit dem Image aus, aus dem er gestartet wurde. |
