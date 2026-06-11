---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---

# Gegeben sind die Grundglieder UND, ODER und NICHT

diese sind nur mit 
1) NAND - Elementen
2) NOR - Elementen
zu realisieren


# 1) NAND

## NICHT realisiert mit NAND
![[image_1741682239706_0 - Copy.png]]

|a|a|z|
|---|---|---|
|0|0|1|
|1|1|0|

$z = \overline{a \land a}$ 

## UND realisiert mit NAND

![[image_1741682239706_0.png]]
$c = \overline{a \land b}$ 
$z = \overline{\overline{a \land b}}$ 

| b   | a   | c   | z   |
| --- | --- | --- | --- |
| 0   | 0   | 1   | 0   |
| 0   | 1   | 1   | 0   |
| 1   | 0   | 1   | 0   |
| 1   | 1   | 0   | 1   |

## ODER realisiert mit NAND

![[13-03-25 12.14.01.excalidraw]]

$z = a \lor b = \overline{\overline{a \lor b}} = \overline{\overline{a} \land \overline{b}}$ 

# 2) NOR

## NICHT realisiert mit NOR
![[NAND und NOR 13-03-25 12.21.53.excalidraw]]

$z = \overline{a \lor a}$ 

| a   | a   | $a \lor a$ | $\overline{a \lor a}$ ($z$) |
| --- | --- | ---------- | --------------------------- |
| 0   | 0   | 0          | 1                           |
| 1   | 1   | 1          | 0                           |

## ODER realisiert mit NOR


![[NAND und NOR 13-03-25 12.27.22.excalidraw]]

$z = \overline{\overline{a \lor b}}$ 

| b   | a   | c   | z   |
| --- | --- | --- | --- |
| 0   | 0   | 1   | 0   |
| 0   | 1   | 0   | 1   |
| 1   | 0   | 0   | 1   |
| 1   | 1   | 0   | 1   |

## UND realisiert mit NOR

![[NAND und NOR 13-03-25 12.35.41.excalidraw]]

$z = a \land b = \overline{\overline{a \land b}} = \overline{\overline{a} \lor \overline{b}}$ 

| a   | b   | c   | d   | z   |
| --- | --- | --- | --- | --- |
| 0   | 0   | 1   | 1   | 0   |
| 0   | 1   | 1   | 0   | 0   |
| 1   | 0   | 0   | 1   | 0   |
| 1   | 1   | 0   | 0   | 1   |
