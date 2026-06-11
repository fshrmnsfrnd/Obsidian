---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---
![[Anwendungen von Schaltnetzen bzw wichtige Schaltnetze 03-04-25 12.43.50.excalidraw]]


| Dezimalziffern | Ein | gänge | BCD | Code |     | Aus | gän | ge  |     |     |     |     |
| -------------- | --- | ----- | --- | ---- | --- | --- | --- | --- | --- | --- | --- | --- |
|                | z   | y     | x   | w    |     | g   | f   | e   | d   | c   | b   | a   |
| 0              | 0   | 0     | 0   | 0    |     | 0   | 1   | 1   | 1   | 1   | 1   | 1   |
| 1              | 0   | 0     | 0   | 1    |     | 0   | 0   | 0   | 0   | 1   | 1   | 0   |
| 2              | 0   | 0     | 1   | 0    |     | 1   | 0   | 1   | 1   | 0   | 1   | 1   |
| 3              | 0   | 0     | 1   | 1    |     | 1   | 0   | 0   | 1   | 1   | 1   | 1   |
| 4              | 0   | 1     | 0   | 0    |     | 1   | 1   | 0   | 0   | 1   | 1   | 0   |
| 5              | 0   | 1     | 0   | 1    |     | 1   | 1   | 0   | 1   | 1   | 0   | 1   |
| 6              | 0   | 1     | 1   | 0    |     | 1   | 1   | 1   | 1   | 1   | 0   | 1   |
| 7              | 0   | 1     | 1   | 1    |     | 0   | 1   | 1   | 0   | 0   | 1   | 1   |
| 8              | 1   | 0     | 0   | 0    |     | 1   | 1   | 1   | 1   | 1   | 1   | 1   |
| 9              | 1   | 0     | 0   | 1    |     | 0   | 0   | 0   | 0   | 1   | 1   | 1   |

Für jedes Anzeigenelement, muss eine Funktionsgleichung aufgestellt werden, um daraus einen BCD-7-Segment-Code-Umsetzer zu entwerfen:

![[Anwendungen von Schaltnetzen bzw wichtige Schaltnetze 03-04-25 13.09.59.excalidraw]]

![[Pasted image 20250508101537.png]]
## Ermitteln der Funktionsgleichung für das Anzeigenelement "a"

| a         | w         | w   | $\bar{w}$ | $\bar{w}$ |           |
| --------- | --------- | --- | --------- | --------- | --------- |
| x         | 1         | 1   | 1         | 1         | $\bar{z}$ |
| x         | x         | x   | x         | x         | z         |
| $\bar{x}$ | 1         | x   | x         | 1         | z         |
| $\bar{x}$ |           | 1   |           | 1         | $\bar{z}$ |
|           | $\bar{y}$ | y   | y         | $\bar{y}$ |           |
### Pseudotetraden:

|     | z   | y   | x   | w   |
| --- | --- | --- | --- | --- |
| 10  | 1   | 0   | 1   | 0   |
| 11  | 1   | 0   | 1   | 1   |
| 12  | 1   | 1   | 0   | 0   |
| 13  | 1   | 1   | 0   | 1   |
| 14  | 1   | 1   | 1   | 0   |
| 15  | 1   | 1   | 1   | 1   |
>Die Pseudotetraden werden mit "don't care" Zustand in das KV-Diagramm eingetragen, da sie nicht auftreten

## KV-Diagramm zusammengefasst:
- Reihe 1+2 = $X$
- Reihe 2+3 = $Z$
- Spalte 2 = $W \land Y$ 
- Spalte 4 = $\bar{W} \land \bar{Y}$


==Funktionsgleichung für das Anzeigeelement "a"==
$a = x \lor z \lor (w \land y) \lor (\bar{w} \land \bar{y})$ 

# Ermitteln der Funktionsgleichung für das Anzeigenelement "b"

| b         | w         | w   | $\bar{w}$ | $\bar{w}$ |           |
| --------- | --------- | --- | --------- | --------- | --------- |
| x         | 1         | 1   |           | 1         | $\bar{z}$ |
| x         | x         | x   | x         | x         | z         |
| $\bar{x}$ | 1         | x   | x         | 1         | z         |
| $\bar{x}$ | 1         |     | 1         | 1         | $\bar{z}$ |
|           | $\bar{y}$ | y   | y         | $\bar{y}$ |           |
## KV-Diagramm zusammengefasst:
- Spalte 1 = $w \land \bar{y}$ 
- Spalte 4 = $\bar{w} \land \bar{y}$ 
- Spalte 1+4 = $\bar{y}$ 
- 4er Block unten links = $\bar{x} \land \bar{w}$
- 4er Block oben rechts = $w \land x$ 

==Funktionsgleichung für das Anzeigeelement "b"== 
$\bar{y}  \lor (\bar{x} \land \bar{w}) \lor (w \land x)$

![[Pasted image 20250508101602.png]]

