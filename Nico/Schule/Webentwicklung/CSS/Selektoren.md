---
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
# Einzelner Selektor

`einfacher Selektor{CSS-Eigenschaften}`
# Selektor Typen

|                   |            |                                            |
| ----------------- | ---------- | ------------------------------------------ |
| Universalselektor | *          | Formatiert alle Elemente                   |
| Typselektoren     | tagname    | Formatiert alle dieser Tags                |
| Klassenselektoren | .classname | Formatiert alle Tags mit class="classname" |
| ID-Selektoren     | `#id`      | Formatiert den Tag mit id="id"             |
# Kombination von Selektoren

## Mehrfachselektor

Gilt für beide Selektoren einzeln
`Selektor1, Selektor2{CSS-Eigenschaften}`

Gilt für Elemente die durch **beide** Selektoren ausgewählt sind
`Selektor1Selektor2{CSS-Eigenschaften}`

## Kombinatoren

| Name                | Syntax                | Beschreibung                                                                                                                                                                                          |
| ------------------- | --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nachfahrselektor    | S1 S2                 | Alle Unterelemente in dem durch selektor1 ausgewählten Element mit der durch selektor2 festgelegten Eigenschaft werden formatiert.                                                                    |
| Kindselektor        | S1>S2                 | Nur die Kind Elemente in dem durch selektor1 ausgewählten Element mit der durch selektor2 festgelegten Eigenschaft werden formatiert. Die Unterelemente der Kinder werden nicht formatiert (Enkel...) |
| Nachbarselektor     | S1+S2                 | Das direkt nach dem durch selektor1 ausgewählte Element mit der durch selektor2 festgelegten Eigenschaft wird formatiert.                                                                             |
| Geschwisterselektor | S1~S2                 | Alle Nachbarelemente des durch selektor1 ausgewählten Elements mit der durch selektor2 festgelegten Eigenschaft werden formatiert.                                                                    |
|                     | `div.classname`       | Div with certain classname                                                                                                                                                                            |
|                     | `div#idname`          | Div with certain ID                                                                                                                                                                                   |
|                     | `div ~ p`             | P tags preceded by div                                                                                                                                                                                |
# Attributselektoren
|                      |                                    |                              |
| -------------------- | ---------------------------------- | ---------------------------- |
| `a[target]`          | With a <yel>target</yel> attribute |                              |
| `a[target="_blank"]` | Open in new tab                    |                              |
| `a[href^="/index"]`  | Starts with <yel>/index</yel>      |                              |
| `[class              | ="chair"]`                         | Starts with <yel>chair</yel> |
| `[class*="chair"]`   | containing <yel>chair</yel>        |                              |
| `[title~="chair"]`   | Contains the word <yel>chair</yel> |                              |
| `a[href$=".doc"]`    | Ends with <yel>.doc</yel>          |                              |
| `[type="button"]`    | Specified type                     |                              |

# Gewichtung von Selektoren (Kaskadierung)

Bei gleicher Gewichtung, wird die zuletzt definierte Eigenschaft übernommen.

## Zähler
Es gibt Zähler A, B, C
Erhöhung bei:

A => ID Selektor
B => Attributselektor, Klassenselektor, Pseudoklassenselektor
C => Typselektor, Pseudoelement


# Pseudoelemente

| Selektor       | Beispiel        | Beschreibung                                    |
| -------------- | --------------- | ----------------------------------------------- |
| ::after        | p::after        | Inhalt hinter jedem `<p>` Element einfügen      |
| ::before       | p::before       | Inhalt vor jedem `<p>` Element einfügen         |
| ::first-letter | p::first-letter | Wählt den ersten Buchstaben von jedem `<p>` aus |
| ::first-line   | p::first-line   | Wählt die erste Zeile von jedem `<p>` aus       |
| ::selection    | p::selection    | Wählt den vom User markierten Bereich aus       |

# Pseudoklassen

Pseudoklassen können an einen Selektor angehängt werden um die Selektion auf einen speziellen Zustand einzuschränken.
## User action pseudo classes
|              |                         |
| ------------ | ----------------------- |
| `a:link    ` | Link in normal state    |
| `a:active  ` | Link in clicked state   |
| `a:hover   ` | Link with mouse over it |
| `a:visited ` | Visited link            |
## Pseudo classes
|                   |                                                                                         |
| ----------------- | --------------------------------------------------------------------------------------- |
| `p::after`        | Add content after p                                                                     |
| `p::before`       | Add content before p                                                                    |
| `p::first-letter` | First letter in p                                                                       |
| `p::first-line`   | First line in p                                                                         |
| `::selection`     | Selected by user                                                                        |
| `::placeholder`   | Placeholder attribute |
| `:root`           | Documents root element                                                                  |
| `:target`         | Highlight active anchor                                                                 |
| `div:empty`       | Element with no children                                                                |
| `p:lang(en)`      | P with en language attribute                                                            |
| `:not(span)`      | Element that's not a span                                                               |
## Input pseudo classes
|                       |                                                                                             |
| --------------------- | ------------------------------------------------------------------------------------------- |
| `input:checked`       | Checked inputs                                                                              |
| `input:disabled`      | Disabled inputs                                                                             |
| `input:enabled`       | Enabled inputs                                                                              |
| `input:focus`         | Input has focus                                                                             |
| `input:in-range`      | Value in range                                                                              |
| `input:out-of-range`  | Input value out of range                                                                    |
| `input:valid`         | Input with valid value                                                                      |
| `input:invalid`       | Input with invalid value                                                                    |
| `input:optional`      | No required attribute                                                                       |
| `input:required`      | Input with required attribute                                                               |
| `input:read-only`     | With readonly attribute                                                                     |
| `input:read-write`    | No read only attribute                                                                       |
| `input:indeterminate` | With indeterminate state |
## Structural pseudo classes
|                         |                            |
| ----------------------- | -------------------------- |
| `p:first-child`         | First child                |
| `p:last-child`          | Last child                 |
| `p:first-of-type`       | First of some type         |
| `p:last-of-type`        | Last of some type          |
| `p:nth-child(2)`        | Second child of its parent |
| `p:nth-child(3n42)`     | Nth-child (an + b) formula |
| `p:nth-last-child(2)`   | Second child from behind   |
| `p:nth-of-type(2)`      | Second p of its parent     |
| `p:nth-last-of-type(2)` | ...from behind             |
| `p:only-of-type`        | Unique of its parent       |
| `p:only-child`          | Only child of its parent   |
