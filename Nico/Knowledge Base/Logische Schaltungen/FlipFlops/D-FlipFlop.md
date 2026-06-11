---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---
# D-FF
>Abgeleitet vom [[SR-FlipFlop|SR-FF]] 
>Bedeutung "d": Delay, d.h. das Eingangssignal wird so lange verzögert, bis das Taktsignal anliegt.
## Schaltzeichen

![[Flipflops 20-05-25 08.35.38.excalidraw]]

## Charakteristische Gleichung
$q_1^{m+1} = d$

## Wahrheitstabelle

| $t^m$ | $t^{m+1}$ |
| ----- | --------- |
| d     | $q^{m+1}$ |
| 0     | 0         |
| 1     | 1         |

# Taktgesteuertes D-FF

![[D-FlipFlop 03-06-25 08.31.48.excalidraw]]

## Wahrheitstabelle

| d   | $q_1$ |
| --- | ----- |
| 0   | 0     |
| 1   | 1     |

| $t^m$ | $t^m$ | $t^{m+1}$   |                     |
| ----- | ----- | ----------- | ------------------- |
| d     | $q_1$ | $q^{m+1}_1$ |                     |
| 0     | 0     | 0           |                     |
| 0     | 1     | 0           |                     |
| 1     | 0     | 1           | $d \land \bar{q_1}$ |
| 1     | 1     | 1           | $d \land \bar{q_1}$ |

=> $q_1^{m+1} = [(d \land \bar{q_1})\lor(d \land q_1)]^m$
=> $q_1^{m+1} = (d \land \bar{q_1})\lor(d \land q_1)$ Charakteristische Gleichung des D-FF
=> $q_1^{m+1} = d$ Charakteristische Gleichung des D-FF vereinfacht

