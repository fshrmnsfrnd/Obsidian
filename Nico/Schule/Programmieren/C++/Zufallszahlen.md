---
Thema:
  - "[[C++]]"
---
# Headerdatei
```cpp
#include <ctime>
```
# Initialisierung
`srand((unsigned) time(nullptr));`
# Erzeugung von Zufallszahlen
`int k = rand();`
# Zahlenbereich
## Menge der möglichen Werte
`int k = rand() % 100;` liefert ganze Zahlen aus von 0 bis 99
>Modulo Anzahl der möglichen Werte
## Anfang der Werte
`int k = rand() % 10 + 1`
>Den Anfangswert addieren / subtrahieren