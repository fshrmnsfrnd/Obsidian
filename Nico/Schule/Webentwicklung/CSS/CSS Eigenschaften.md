---
Fach:
tags:
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
# [[Werte]]

Die meisten Eigenschaften bekommen einen Wert zugewiesen.
# Alle Eigenschaften

## Eigenschaften eines Elements zurücksetzen

| all | Setzt alle Eigenschaften, die einem Element zugewiesen wurden, zurück auf die initialen [[Werte]]. |
| --- | -------------------------------------------------------------------------------------------------- |
## CSS-Animation

Hier können oft [[Werte#Zeitmaße|Zeitmaße]] angegeben werden.

| Name                          | Beispiel                                             | Beschreibung                                                                                                    |
| ----------------------------- | ---------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| **animation**                 | `.qualm { animation: smoke 5s; }`                    | Deklariert eine Keyframe-Animation, die eine oder mehr Eigenschaften an einem oder mehreren Zeitpunkten ändert: |
| **animation-delay**           | `.qualm { animation: smoke 5s 1s; }`                 | Verzögerung des Starts, z. B. für die Synchronisation von Animationen:                                          |
| **animation-direction**       | `.qualm { animation: smoke 5s alternate infinite; }` | Einfacher, zyklischer, umgekehrter oder alternierender (hin- und zurück) Ablauf:                                |
| **animation-duration**        | `.qualm { animation: smoke 5s; }`                    | Dauer eines vollständigen Zyklus in Sekunden:                                                                   |
| **animation-fill-mode**       | `.qualm { animation: smoke 5s forwards; }`           | Stile am Ende der Animation zurücksetzen oder beibehalten:                                                      |
| **animation-iteration-count** | `.qualm { animation: smoke 5s infinite; }`           | Anzahl der Wiederholungen:                                                                                      |
| **animation-name**            | `.qualm { animation: smoke 5s; }`                    | Name der `@keyframes`-Animation:                                                                                |
| **animation-play-state**      | `.element { animation-play-state: paused; }`         | Zustand der Animation: laufend oder pausiert:                                                                   |
| **animation-timing-function** | `.qualm { animation: smoke 5s ease-in; }`            | Gleichmäßiger Ablauf, beschleunigt oder abgebremst:                                                             |
## background – Hintergrundfarbe

Hier werden häufig [[Werte#Längen|Längenangaben]] verwendet.

| Name                      | Beschreibung                                                                                     | Beispiel                                                          |
| ------------------------- | ------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------- |
| **background**            | Kurzschrift – fasst mehrere Eigenschaften des Hintergrunds zusammen:                             | `elem { background: ivory url(background-image.jpg) repeat-x; }`  |
| **background-attachment** | Hintergrund steht fest oder scrollt:                                                             | `elem { background-attachment: fixed; }`                          |
| **background-clip**       | Beschneidet das Hintergrundbild:                                                                 | `elem { background-clip: border-box; }`                           |
| **background-color**      | Hintergrundfarbe eines Elements:                                                                 | `elem { background-color: ivory; }`                               |
| **background-image**      | Hintergrundbild:                                                                                 | `elem { background-image: url(background-image.jpg) no-repeat; }` |
| **background-origin**     | Reichweite und die Position von Hintergrundbildern (`border-box`, `padding-box`, `content-box`): | `elem { background-origin: content-box; }`                        |
| **background-position**   | Position und Ausrichtung des Hintergrundbilds:                                                   | `elem { background-position: left top; }`                         |
| **background-repeat**     | Hintergrundbild wiederholen:                                                                     | `elem { background-repeat: repeat-x; }`                           |
| **background-size**       | Skaliert Hintergrundbilder oder passt Hintergrundbilder an die Größe des Viewports an:           | `elem { background-size: cover; }`                                |
## Rahmen (border)
Hier werden häufig [[Werte#Längen|Längenangaben]] verwendet.

| Name                    | Beschreibung                                                                    | Beispiel                                                |
| ----------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------- |
| **border**              | Kurzschrift – fasst `border-width`, `border-style` und `border-color` zusammen: | `elem { border: 1px solid black; }`                     |
| **border-bottom**       | Kurzschrift für den unteren Rand:                                               | `elem { border-bottom: 2px dashed red; }`               |
| **border-bottom-color** | Farbe des unteren Rands:                                                        | `elem { border-bottom-color: blue; }`                   |
| **border-bottom-style** | Stil des unteren Rands:                                                         | `elem { border-bottom-style: dotted; }`                 |
| **border-bottom-width** | Breite des unteren Rands:                                                       | `elem { border-bottom-width: 3px; }`                    |
| **border-collapse**     | Definiert, ob Tabellenränder zusammenfallen oder getrennt bleiben:              | `table { border-collapse: collapse; }`                  |
| **border-color**        | Farbe der Rahmen:                                                               | `elem { border-color: red blue green yellow; }`         |
| **border-image**        | Definiert ein Bild als Rahmen:                                                  | `elem { border-image: url(border.png) 30 round; }`      |
| **border-radius**       | Rundung der Ecken eines Elements:                                               | `elem { border-radius: 10px; }`                         |
| **border-style**        | Stil der Rahmenlinie:                                                           | `elem { border-style: dotted; }`                        |
| **border-width**        | Breite der Rahmenlinie:                                                         | `elem { border-width: 2px; }`                           |
| **box-shadow**          | Hinzufügen eines Schattens zu einem Element:                                    | `elem { box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.5); }` |
## Breite und Höhe (width, height)

Hier werden häufig [[Werte#Längen|Längenangaben]] verwendet.


| Name           | Bescheibung                     | Beispiel                      |
| -------------- | ------------------------------- | ----------------------------- |
| **width**      | Breite eines Elements:          | `elem { width: 100px; }`      |
| **height**     | Höhe eines Elements:            | `elem { height: 200px; }`     |
| **max-width**  | Maximale Breite eines Elements: | `elem { max-width: 500px; }`  |
| **max-height** | Maximale Höhe eines Elements:   | `elem { max-height: 300px; }` |
| **min-width**  | Minimale Breite eines Elements: | `elem { min-width: 100px; }`  |
| **min-height** | Minimale Höhe eines Elements:   | `elem { min-height: 150px; }` |
## Farben und Transparenz (Color, opacity)

| Name        | Beschreibung                | Beispiel                    |
| ----------- | --------------------------- | --------------------------- |
| **Color**   | Textfarbe eines Elements:   | `elem { color: #3333333; }` |
| **opacity** | Transparenz eines Elements: | `elem { opacity: 0.5; }`    |
## Listen

| Name           | Bescheibung                    | Beispiel                            |
| -------------- | ------------------------------ | ----------------------------------- |
| **List-Style** | Bild als Aufzählungszeichen    | `list-style-image: url(/bild.png);` |
| List-Style     | Zeichen als Aufzählungszeichen | `list-style-type: "*";`             |
#### n-te Element

| Name                   | Beschreibung         | Beispiel                 |
| ---------------------- | -------------------- | ------------------------ |
| Festes Element         | Das zweite Element   | `.class:nth-child(2){}`  |
| Wiederholendes Element | Jedes zweite Element | `.class:nth-child(2n){}` |
