---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---
>Setzen-Rücksetzen FlipFlop

# Einflanken gesteuerte SR-FF
("C" = Clock = Takt)
![[Flipflops 20-05-25 09.03.52.excalidraw]]

# SR-FF mit dominierendem R Eingang
**Motivation**: Verbotene Zustände s = r = 1 mit dem Ziel q = 0

![[Flipflops 15-05-25 12.05.20.excalidraw]]

## Wahrheitstabelle

| $t^m$ | $t^m$ | $t^{m+1}$ |                      |
| ----- | ----- | --------- | -------------------- |
| r     | s     | $q^{m+1}$ |                      |
| 0     | 0     | $q^m$     | Speicherfall         |
| 0     | 1     | 1         | Setzen               |
| 1     | 0     | 0         | Rücksetzen           |
| 1     | 1     | 0         | Rücksetzen dominiert |
## Charakteristische Gleichung
$q^{m+1} =  \bar{r} \land (s \lor q)$ 

# SR-FF ohne dominierenden Eingang

## Wahrheitstabelle
| r   | s   | $q^{m+1}$         | **Bemerkung**          |
| --- | --- | ----------------- | ---------------------- |
| 0   | 0   | $q^m$             | Speicherfall           |
| 0   | 1   | 1                 | Setzen                 |
| 1   | 0   | 0                 | Rücksetzen             |
| 1   | 1   | **nicht erlaubt** | **Verbotener Zustand** |
## Charakteristische Gleichung
$q^{m+1} = s \lor (\bar{r} \land q^m)$

# Schaltzeichen

![[Flipflops 13-05-25 09.11.20.excalidraw]]

# Wahrheitstabelle eines taktgesteuerten SR-Flipflop

|                  | $t$ | $r$ | $s$ | $q$ | $\bar{q}$ |
| ---------------- | --- | --- | --- | --- | --------- |
| X = Speicherfall | 0   | 0   | 0   | X   | X         |
|                  | 0   | 0   | 1   | X   | X         |
|                  | 0   | 1   | 0   | X   | X         |
|                  | 0   | 1   | 1   | X   | X         |
|                  | 1   | 0   | 0   | X   | X         |
| Setzen ->        | 1   | 0   | 1   | 1   | 0         |
| Rücksetzen ->    | 1   | 1   | 0   | 0   | 1         |
| Verboten ->      | 1   | 1   | 1   | /   | /         |

Führt man $t^m$ als Zeitpunkt eines Taktimpulses und $t^{m+1}$ als Zeitpunkt des nachfolgenden Taktpulses ein, so können Wahrheitstabellen wie folgt dargestellt werden. 

| $t^m$ |     |       | $t^{m+1}$ |              |
| ----- | --- | ----- | --------- | ------------ |
| $r$   | $s$ | $q^m$ | $q^{m+1}$ |              |
| 0     | 0   | 0     | 0         | Speicherfall |
| 0     | 0   | 1     | 1         | Speicherfall |
| 0     | 1   | 0     | 1         | Setzen       |
| 0     | 1   | 1     | 1         | Setzen       |
| 1     | 0   | 0     | 0         | Rücksetzen   |
| 1     | 0   | 1     | 0         | Rücksetzen   |
| 1     | 1   | 0     |           | Verboten     |
| 1     | 1   | 1     |           | Verboten     |
# Zeitablauf Diagramm SR-FF mit dominierendem Rücksetzeingang (Taktzustands und flanken gesteuert)
![[Pasted image 20250515130632.png]]

