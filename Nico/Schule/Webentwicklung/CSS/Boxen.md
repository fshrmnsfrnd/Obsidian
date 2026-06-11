---
tags:
Fach:
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
# Tags 
---
## Inline Element
```
<span></span>
```
## Block Element
```
<div></div>
```
# Modell
---
![[Pasted image 20241125110825.png]]
# Größe von Boxen
---
## Box Sizing
```css
box-sizing: border-box; //Border-Box ( width = content+padding+border )
box-sizing: content-box; //Standard-Box (width = content = Gesamtbreite – padding - border - margin)
```
## Margin und Padding
---
>Hier mit `margin`, geht genauso mit `padding`

**Alle Ränder gleich:**
`margin: 5px;
**Alle Ränder unterschiedlich:**
```css
margin: 1px 2px 3px 4px;
```
Reihenfolge: oben, rechts, unten, links
**Alle Ränder einzeln**:
```css
margin-top: 1px;
margin-right: 2px;
margin-bottom: 3px;
margin-left: 4px;
```
## Rand
```css
border: 5px solid black;
```
Dicke des Rahmens, Muster, Farbe
## Overflow

| `visible` | Der Inhalt ragt aus dem Element heraus. Der gesamte Inhalt ist sichtbar.                                                              |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `hidden`  | Der Inhalt wird abgeschnitten. Teile des Inhalts sind nicht sichtbar.                                                                 |
| `scroll`  | Der Inhalt wird abgeschnitten. Der Browser sollte allerdings Scrolleisten anzeigen, damit der Rest des Inhalts angezeigt werden kann. |
| `auto`    | Der Browser macht es so, wie er „will“.                                                                                               |
# Box Typen
---
Der Box Typ wird über die Eigenschaft `display` geändert.
Es gibt die Typen:
- [[Flexbox]]
	- `flex`
- [[Grid|Grid Layout]]
	- `grid`
- [[Tabellen]]
	- `table`
- Ausgeblendet
	- `none`

Es gibt auch [[Floating Boxes]] diese sind aber veraltet.