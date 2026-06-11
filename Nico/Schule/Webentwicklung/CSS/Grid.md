---
Fach:
tags:
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
`display: grid`
# CSS Eigenschaften
---

| Eigenschaft            | Beschreibung                                                                                                                                                                                    |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `column-gap`           | Abstand zwischen den Spalten                                                                                                                                                                    |
| `row-gap`              | Abstand zwischen den Zeilen                                                                                                                                                                     |
| `justify-items`        | richtet alle Elemente eines Grids horizontal aus.                                                                                                                                               |
| `align-items`          | richtet alle Elemente eines Grids vertikal aus.                                                                                                                                                 |
| `grid-column`          | An welcher Position das Element angezeigt wird.<br>Mit `/` kann von bis angegeben werden.                                                                                                       |
| `grid-row`             | An welcher Position das Element angezeigt wird.<br>Mit `/` kann von bis angegeben werden.                                                                                                       |
| `grid-template-areas`  | Pro Zeile einen String angeben, hier können jeweils die Spalten stehen z.B.: <br>``"h h h"`` <br>``"left content right"`` <br>``"footer footer footer"``                                        |
| `grid-area`            | Hier wird die ID für `grid-template-areas` angegeben z.B. content                                                                                                                               |
# Colums and Rows
---
Um Anzahl und Höhe/Breite der Zeilen und Spalten festzulegen verwendet man `grid-template-rows` und `grid-template-colums`.
## Werte für Größen von Columns und Rows

| Value                        | Beschreibung                                                                                                                                                             |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `auto`                       | Die Breite/Höhe wird an den Inhalt angepasst                                                                                                                             |
| `1fr`                        | Der Bereich wird in die gesamte Anzahl der Teile pro Zeile aufgeteilt und danach die Breite der einzelnen Spalten bestimmt.                                              |
| `px`                         | Feste Längenangabe. Auch andere Einheiten wie Prozent sind möglich                                                                                                       |
| `repeat(<anzahl>, <breite>)` | Es werden `<anzahl>` Spalten/Reihen mit der angegebenen Breite/Höhe erstellt. Wenn für die Anzahl auto-fill angegeben wird, werden so viele Spalten wie möglich erzeugt. |
| `minmax(<min>,<max>)`        | gibt die minimale bzw. maximale Breite einer Spalte an.                                                                                                                  |
# Gap
---

| CSS               | Description                                       |
| ----------------- | ------------------------------------------------- |
| `gap: 1px`        | Abstand zwischen Zellen in allen Richtungen = 1px |
| `gap: 1px 2px`    | Vertikal 1px und Horizontal 2px                   |
| `row-gap: 1px`    | Vertikal 1px                                      |
| `column-gap: 2px` | Horizontal 2px                                    |
# Statische Areas
---
```css
#container{
	display: grid;
	grid-template-areas:
	"box1 box1"
	"box2 box3"
	;
}

#element1{
	grid-area: box1;
}

#element2{
	grid-area: box2;
}

#element3{
	grid-area: box3;
}
```

> [!WARNING] Die Bezeichner müssen mit einem Buchstaben anfangen
# Grid Cells (Children)
---
Funktioniert gleich mit Row

```css
/*grid-column: grid-column-start / grid-column-end;*/
grid-column: 1 / span 2; /*Start in Column 1 span over 2 Columns/
/*oder*/
grid-column-start: 1;
grid-column-end: span 2;
```

> [!NOTE] Es ist auch `max` möglich (wählt die letzte Zelle in der Spalte/Zeile aus)

```css
/*grid-column: grid-column-start;*/
grid-column: 3; /*Start in Column 3*/
/*oder*/
grid-column-start: 3;
```

```css
/*grid-column: grid-column-end;*/
grid-column: span 2; /*Span over 2 Columns/
/*oder*/
grid-column-end: span 2;
```
# Subgrid
---
```css
.grid {
  display: grid;
  grid-template-columns: repeat(9, 1fr);
  grid-template-rows: repeat(4, minmax(100px, auto));
}

.item {
  display: grid;
  grid-column: 2 / 7;
  grid-row: 2 / 4;
  grid-template-columns: subgrid;
  grid-template-rows: repeat(3, 80px);
}

.subitem {
  grid-column: 3 / 6;
  grid-row: 1 / 3;
}
```