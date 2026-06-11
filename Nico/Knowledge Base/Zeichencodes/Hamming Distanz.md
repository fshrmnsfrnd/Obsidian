---
Fach:
tags:
Thema:
  - "[[Zeichencodes]]"
---
>Alle 4 Tetraden Codes lassen in ihrer Grundform keine Fehlererkennung zu. Jede Bitänderung führt zu einem neuen definierten Bitmuster.
>
>Fehlererkennende Codes haben die Eigenschaft, sich in möglichst vielen Bitstellen zu unterscheiden.
>Wird ein einzelnes Codewort bei einer Übertragung verfälscht, so entsteht ein nicht verwendetes Bitmuster.
>
>**m - aus - n - Codes**
>
>n: Länge des Codeworts
>m: Anzahl der mit 1 belegten Stellen

| Zeilen | Dezimal | 7   | 4   | 2   | 1   | 0   |
| ------ | ------- | --- | --- | --- | --- | --- |
| A      | 0       | 1   | 1   | 0   | 0   | 0   |
| B      | 1       | 0   | 0   | 0   | 1   | 1   |
| C      | 2       | 0   | 0   | 1   | 0   | 1   |
| D      | 3       | 0   | 0   | 1   | 1   | 0   |
| E      | 4       | 0   | 1   | 0   | 0   | 1   |
| F      | 5       | 0   | 1   | 0   | 1   | 0   |
| G      | 6       | 0   | 1   | 1   | 0   | 0   |
| H      | 7       | 1   | 0   | 0   | 0   | 1   |
| I      | 8       | 1   | 0   | 0   | 1   | 0   |
| J      | 9       | 1   | 0   | 1   | 0   | 0   |

==Hamming-Distanz== ist die Anzahl der unterschiedlichen Bits zweier Codewörter
**Bsp.:**
0101
0011
Unterschied an 2 Bitstellen
=> h=2 (Hamming-Distanz)

## Vergleich von Codewörtern

1. Jedes Codewort mit jedem Vergleichen
2. Jeweils die Hamming Distanz bestimmen
3. Die niedrigste Hamming Distanz h$_{min}$ raussuchen
4. Es kann ein Fehler $k$ weniger bestimmt werden als h$_{min}$ 
