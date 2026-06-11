---
tags:
Fach: "[[BA]]"
Thema:
  - "[[Linux]]"
---
# Berechtigungen anzeigen
`ls -l`
# Bedeutung

|             | r            | w                                         | x                    |
| ----------- | ------------ | ----------------------------------------- | -------------------- |
| Datei       | Inhalt lesen | Dateiinhalt ändern                        | Datei ausführen      |
| Verzeichnis | Inhalt lesen | Dateien / Verzeichnisse erstellen/löschen | Verzeichnis betreten |
## Oktalwerte

| 4   | 2   | 1   |
| --- | --- | --- |
| r   | w   | x   |
# Berechtigung ändern
```
chmod 754 DATEI # rwx r-x r-- 
chmod +x DATEI # [[user]], group und others erhalten zusätzlich x 
chmod u-w DATEI # user wird w entfernt
```
# Besitzer ändern
`chown <user> <datei>`
# Gruppe ändern
`chgrp <group> <datei>`
# Beides gleichzeitig
`chown <user:group> <datei>`
# Standardwerte
>Standardwerte werden Festgelegt durch die Maximale Berechtigung minus den umask Wert
# UMASK
Der [[Console#umask|umask]] Standardwert Beträgt 022.
Er kann mit `umask <wert>` geändert werden.

| Datei       | Verzeichnis |
| ----------- | ----------- |
| 644         | 755         |
| rw- r-- r-- | rwx r-x r-x |
