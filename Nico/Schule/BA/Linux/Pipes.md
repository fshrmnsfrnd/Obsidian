---
tags:
Fach: "[[BA]]"
Thema:
  - "[[Linux]]"
---
# unbenannte Pipes
`Command1 | Command2`
>Die Ausgabe von Command1 wird als Eingabe an Command2 übergeben
# Den Ausgabekanal duplizieren
`Command | tee log.txt` 
Schreibt den Output von `Command` sowohl auf den Bildschirm als auch in die Datei `log.txt`