---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---
>Trigger FlipFlop

![[Flipflops 20-05-25 09.32.36.excalidraw]]
# Schaltzeichen
![[Flipflops 20-05-25 09.41.37.excalidraw]]

# Wahrheitstabelle

| $t^m$ | $t^{m+1}$ |
| ----- | --------- |
| $q$   | $q^{m}$   |
| 0     | 1         |
| 1     | 0         |

|   t | $q^m$ | $q^{m+1}$ | Bemerkung |
| --: | ----- | --------- | --------- |
|   0 | 0     | 0         | Halten    |
|   0 | 1     | 1         | Halten    |
|   1 | 0     | 1         | Toggle    |
|   1 | 1     | 0         | Toggle    |
# Charakteristische Gleichung
$q^{m+1} = (t \land \bar{q}) \lor (\bar{t} \land q)$
