---
Fach:
tags:
Thema:
  - "[[Zeichencodes]]"
---
>Jedem Codewort wird ein Bit so hinzugefügt, dass die Summe der im Wort vorkommenden 1er entweder auf eine gerade (even) oder eine ungerade (odd) Zahl ergänzt

Beispiel:
Hex Ziffern (odd Parity Check)

| Zahl  | Code | Prüfbit |
| ----- | ---- | ------- |
| 0     | 0000 | 1       |
| 1     | 0001 | 0       |
| 2     | 0010 | 0       |
| 3     | 0011 | 1       |
| 4     | 0100 | 0       |
| 5     | 0101 | 1       |
| 6     | 0110 | 1       |
| 7     | 0111 | 0       |
| 8     | 1000 | 0       |
| 9     | 1001 | 1       |
| A<br> | 1010 | 1       |
| B     | 1011 | 0       |
| C     | 1100 | 1       |
| D     | 1101 | 0       |
| E     | 1110 | 0       |
| F     | 1111 | 1       |

- Nur ein Fehler erkennbar
- nicht erkennbar, wo der Fehler ist

# Odd Parity Check mit Tabelle

![[src/Parity Check 19-01-25 18.28.16.excalidraw]]

- Ein Bitfehler im Block kann erkannt und lokalisiert werden