---
tags:
Fach: "[[BA]]"
Thema:
  - "[[Linux]]"
---
# Inhalt lesen

## gesamten Inhalt zeigen

[[Console#cat|Cat]] kann den Inhalt auf der Konsole zeigen

## Anfang lesen

[[Console#Head|head]] zeigt den Anfang einer Datei an. mit `-n` kann die Anzahl der Zeilen Festgelegt werden

## Ende lesen

[[Console#Tail|tail]] zeigt das Ende einer Datei an. mit `-n` kann die Anzahl der Zeilen Festgelegt werden
#### Automatische Aktualisierung mit Tail
mit `-f` aktualisiert sich der Text, wenn sich die Datei ändert.

# Inhalt ändern

## Text in Datei überschreiben
`echo 'Text' > DATEI 
## Am Ende KEINEN Zeilenumbruch anfügen 
`echo -n 'Text' > DATEI 
## Text an Datei anhängen 
`echo 'Text' >> DATEI

oder mit [[VI]]
