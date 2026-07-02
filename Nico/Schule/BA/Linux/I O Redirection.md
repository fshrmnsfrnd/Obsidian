---
tags:
Fach: "[[BA]]"
Thema:
  - "[[Linux]]"
---
# Kanäle
---

| Name   | Kanal                        | Dateideskriptor |
| ------ | ---------------------------- | --------------- |
| stdin  | Standardeingabe (Tastatur)   | 0               |
| stdout | Standardausgabe (Bildschirm) | 1               |
| stderr | Standardfehler (Bildschirm)  | 2               |
# Output in Datei umlenken
---
`>` leitet standardmäßig den Kanal 1 an die Datei um
### Inhalt der Datei überschreiben
`ls ./ 1> log.txt`
### An Datei anhängen
`ls ./ 1>> log.txt`
## beide Kanäle umlenken
### in eine Datei
`ls > log.txt 2>&1`
### in einzelne Dateien
`ls 1> log.txt 2> error.log`
# Eingabe in Datei umleiten
---
`ls < log.txt`