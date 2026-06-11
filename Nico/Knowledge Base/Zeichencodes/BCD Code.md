---
Fach:
tags:
Thema:
  - "[[Zeichencodes]]"
---

>Tetraden Codes stellen die einzelnen Dezimalen Ziffern Binär mit 4 Bit dar. 
>Das ergibt, dass die binären Werte von $10_{10}$ bis $15_{10}$ nicht verwendet werden (Pseudotetraden) 


### Beispiel

| Dezimal       | 2    | 9    | 5    |
| ------------- | ---- | ---- | ---- |
| Tetraden Code | 0010 | 1001 | 0101 |
# Addition

>Normales addieren, solange der Bereich nicht in eine Pseudotetrade fällt

![[Tetradencodes 2024-12-27 14.21.27.excalidraw]]

## Korrekturaddition

> [!NOTE]
> Fällt der Wert eines Nibbles in den Bereich einer Pseudotetrade muss ein Korrekturaddition mit 0110 (6), bei der Tetrade aus der der Überlauf kommt, durchgeführt werden.


![[Tetradencodes 27-12-24 14.28.23.excalidraw]]

# Subtraktion
Bei der Subtraktion wird das Zehnerkomplement addiert.
## Zehnerkomplement bilden
10$_{10}$ bzw. 1010$_{2}$ minus den Wert der Zahl

## Vorzeichen bestimmen
Ergibt sich bei der Addition ==kein== Übertrag in die 5te Stelle, ist das Ergebnis negativ, und es muss das 10er [[Komplement]] des Ergebnisses gebildet werden, um den wahren Wert des Ergebnisses zu erhalten.

### Beispiel
![[Tetradencodes 29-12-24 15.44.06.excalidraw]]

