---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---
>Jump n Kill FlipFlop

# Einflanken gesteuertes JK-FF 
>abgeleitet vom SR-FF

**Ziel**: Vielseitiges FF
**Verhalten:** 
- Setzen/Rücksetzen, wie das RS-FF
- "Verbotene Fall" -> Toggled, wie T-FF

![[Flipflops 22-05-25 12.08.39.excalidraw]]

## Schaltzeichen
![[Flipflops 22-05-25 12.14.01.excalidraw]]

## Wahrheitstabelle
| $t^m$ |     | $t^{m+1}$         |
| ----- | --- | ----------------- |
| $k$   | $j$ | $q^{m+1}$         |
| 0     | 0   | $q^m$             |
| 0     | 1   | 1                 |
| 1     | 0   | 0                 |
| 1     | 1   | $\overline{q^m}$  |
## Charakteristische Gleichung
$q^{m+1} = (j \land \overline{q}) \lor (\bar{k} \land q)$

# JK-FF mit zusätzlichem Setzen / Rücksetzen (taktunabhängig)

![[JK-FlipFlop 24-06-25 08.24.48.excalidraw]]

| $t^m$ |     | $t^{m+1}$        |
| ----- | --- | ---------------- |
| K     | J   | $q^{m+1}$        |
| 0     | 0   | $q^m$            |
| 0     | 1   | 1                |
| 1     | 0   | 0                |
| 1     | 1   | $\overline{q^m}$ |
## Vereinfachte charakteristische Gleichung

$q^{m+1} = (j \land \bar{q}) \lor (\bar{k} \land q)$

# Ausführliche Wahrheitstabelle

| $t^m$ |     |       | $t^{m+1}$ |                                 |            |
| ----- | --- | ----- | --------- | ------------------------------- | ---------- |
| K     | J   | $q^m$ | $q^{m+1}$ |                                 |            |
| 0     | 0   | 0     | 0         |                                 | speichern  |
| 0     | 0   | 1     | 1         | $q \land \bar{j} \land k$       | speichern  |
| 0     | 1   | 0     | 1         | $\bar{q} \land j \land \bar{k}$ | setzen     |
| 0     | 1   | 1     | 1         | $q \land j \land \bar{k}$       | setzen     |
| 1     | 0   | 0     | 0         |                                 | Rücksetzen |
| 1     | 0   | 1     | 0         |                                 | Rücksetzen |
| 1     | 1   | 0     | 1         | $\bar{q} \land j \land k$       | Toggeln    |
| 1     | 1   | 1     | 0         |                                 | Toggeln    |
-> ODER Normalform

$q^{m+1} = [(q \land \bar{j} \land k) \lor (\bar{q} \land j \land \bar{k}) \lor (q \land j \land \bar{k}) \lor (\bar{q} \land j \land k)]^m$ 
$q^{m+1} = (j \land \bar{q}​) \lor (\bar{k} \land q)$


[[BCD-Synchronzähler (4-Bit) mit JK-FF]]
