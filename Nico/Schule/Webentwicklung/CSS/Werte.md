---
tags:
Fach:
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
# Berechnen
---
```css
width: calc(100% - 2px);
```
# Längen
---
<table>
<tbody><tr>
<th>Einheit
</th>
<th>Name
</th>
<th> Größe
</th></tr>
<tr>
<th> cm
</th>
<td> Zentimeter
</td>
<td>1&nbsp;cm = 37,8 Pixel (gerundet)
</td></tr>
<tr>
<th> mm
</th>
<td> Millimeter
</td>
<td>0,1&nbsp;cm = 3,78 Pixel (gerundet)
</td></tr>
<tr>
<th> Q
</th>
<td> Quarter-millimeters
</td>
<td> 1Q = 1/4mm
</td></tr>
<tr>
<th> in
</th>
<td>Zoll
</td>
<td> 2,54&nbsp;cm ≙ 96 Pixel
</td></tr>
<tr>
<th>pc
</th>
<td> Pica
</td>
<td> 1/6 Zoll ≙ 16 Pixel
</td></tr>
<tr>
<th> pt
</th>
<td> Punkt
</td>
<td>1/72 Zoll ≙ 1,33 Pixel (gerundet)<br>ca. 0,3133 mm im Drucklayout
</td></tr>
<tr>
<th> px
</th>
<td> Ein <b>CSS-Pixel</b> ist der sichtbare Bereich eines Pixel auf einem Gerät mit einer Punktdichte von 96 DPI und einer Armlänge Abstand vom Leser.
</td>
<td><i>variabel</i> ≙ 0,75 Punkt = 1/96in
</td></tr></tbody></table>

## Relative Längenmaße

### Relativ zur Schriftgröße

| em  | Schriftgröße des Eltern-Elements, wenn es sich um typografische Eigenschaften wie font-size handelt, und Schriftgröße des Elements selbst, wenn es sich um andere Eigenschaften wie width handelt.                                                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ex  | entspricht der Größe des Kleinbuchstabens "x". Sofern die verwendete Schriftart eine _x-Höhe_ definiert, wird dieser Wert verwendet. Andernfalls entspricht ein `ex` genau einem halben em (0.5em).                                                           |
| ch  | entspricht der Breite der Ziffer "0". Sofern die verwendete Schriftart eine _Null-Breite_ definiert, wird dieser Wert verwendet. Andernfalls wird versucht die durchschnittliche Breite aller Zeichen zu berechnen, sodass dieser Wert verwendet werden kann. |
| lh  | entspricht der line-height des Elements                                                                                                                                                                                                                       |
### Relativ zur [[Viewport|Viewportgröße]]

| vw   | entspricht 1% der Viewport-Breite                                                                                                                                                                                          |
| ---- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| vh   | entspricht 1% der Viewport-Höhe                                                                                                                                                                                            |
| vb   | entspricht 1% der Viewportabmessung in Block-Richtung (bei horizontaler Schrift: vh; bei vertikaler Schrift: vw)                                                                                                           |
| vi   | entspricht 1% der Viewportabmessung in Inline-Richtung (bei horizontaler Schrift: vw; bei vertikaler Schrift: vh)                                                                                                          |
| lvh  | entspricht 1% der Höhe des großen Viewports, d.h. wenn auf Mobilgeräten Adressleiste und Menüleiste nicht angezeigt werden                                                                                                 |
| svh  | entspricht 1% der Höhe des kleinen Viewports, d.h. wenn auf Mobilgeräten Adressleiste und Menüleiste angezeigt werden und Platz beanspruchen                                                                               |
| dvh  | entspricht 1% der Höhe des dynamischen Viewports                                                                                                                                                                           |
| vmin | entspricht 1% der Viewport-Minimalabmessung (Breite oder Höhe, je nachdem, welcher Wert der kleinere ist)                                                                                                                  |
| vmax | entspricht 1% der Viewport-Maximalabmessung (Breite oder Höhe, je nachdem, welcher Wert der größere ist)                                                                                                                   |
| rem  | Ein rem (root-em =Wurzel-Em) entspricht der Schriftgröße, die für das Wurzelelement (in HTML das html-Element festgelegt wurde.  <br>(Evtl. Änderungen der Schriftgröße in Elternelementen können so übersprungen werden.) |
### Relativ zum Containerelement

| cqw                                                                                                               | entspricht 1% der Container-Breite                                                                                                                                                                                                                                                                                                                                                              |
| ----------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| cqh                                                                                                               | entspricht 1% der Container-Höhe                                                                                                                                                                                                                                                                                                                                                                |
| cqb                                                                                                               | entspricht 1% der Container-Abmessung in Block-Richtung (bei horizontaler Schrift: cqh; bei vertikaler Schrift: cqw)                                                                                                                                                                                                                                                                            |
| cqi                                                                                                               | entspricht 1% der Container-Abmessung in Inline-Richtung (bei horizontaler Schrift: cqw; bei vertikaler Schrift: cqh)                                                                                                                                                                                                                                                                           |
| cqmin                                                                                                             | entspricht 1% der Container-Minimalabmessung (Breite oder Höhe, je nachdem, welcher Wert der kleinere ist)                                                                                                                                                                                                                                                                                      |
| cqmax                                                                                                             | entspricht 1% der Container-Maximalabmessung (Breite oder Höhe, je nachdem, welcher Wert der größere ist)                                                                                                                                                                                                                                                                                       |
# Winkelmaße
---
<table>
<tbody><tr>
<th>Einheit
</th>
<th>Beschreibung
</th>
<th>Beispiel
</th></tr>
<tr>
<th> deg
</th>
<td> <b>Grad (°)</b>, Ein Vollwinkel, also eine Kreisumrundung, entspricht 360°.
</td>
<td><code>transform: rotate(45deg);</code>
</td></tr>
<tr>
<th> grad
</th>
<td>100 <b>grad</b> (in der Mathematik als gon bekannt) entsprechen einer 90°-Drehung, also einem rechten Winkel. Eine Kreisumrundung entspricht somit 400 gon, also <code>400grad</code>.
</td>
<td><code>rotate: 75grad;</code>
</td></tr>
<tr>
<th> rad
</th>
<td>Ein <b>Radiant</b> entspricht einer Drehung, bei dem der Winkel durch die Länge des entsprechenden Kreisbogens im Einheitskreis angegeben wird. Eine Kreisumrundung entspricht somit <code>2π rad</code>.
</td>
<td><code>rotate: 2.5rad;</code>
</td></tr>
<tr>
<th> turn
</th>
<td>Ein <b>Vollwinkel</b> entspricht einer Kreisumrundung.
</td>
<td><code>rotate: .75turn;</code>
</td></tr></tbody></table>

# Zeitmaße
---
<table>
<tbody><tr>
<th>Einheit
</th>
<th>Beschreibung
</th></tr>
<tr>
<th> s
</th>
<td> Sekunde.
</td></tr>
<tr>
<th> ms
</th>
<td> Eine Millisekunde entspricht dem 1000. Teil einer Sekunde.
</td></tr></tbody></table>