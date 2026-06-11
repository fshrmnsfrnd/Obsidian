---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---
Darstellung und Vereinfachung der ==Disjunktiven Normalform== (KDFN). Entwicklung durch Karnaugh / Veitch.
# Beispiel 1
$a ; b => n = 2 => 2^2 = 4$

| z         | $a$ | $\bar{a}$ |
| --------- | --- | --------- |
| $b$       | 0   | 0         |
| $\bar{b}$ | 1   | 1         |
Funktionsgleichung $z = (a \land \bar{b})\lor(\bar{a} \land \bar{b})$
$z = \bar{b}$ 
# KV - Diagramme für 3 Variablen
Mit n = 3 sind $2^n = 2^3 = 8$ verschiedene Vollkonjunktionen möglich

|           | $a$       | $a$ | $\bar{a}$ | $\bar{a}$ |
| --------- | --------- | --- | --------- | --------- |
| $b$       |           |     |           |           |
| $\bar{b}$ |           |     |           |           |
|           | $\bar{c}$ | c   | c         | $\bar{c}$ |
Bündelungen dürfen mit 2, 4 oder 8 benachbarten Vollkonjunktionen erfolgen. Die jeweils äußeren Felder einer Zeile gelten zueinander benachbart. 

## Beispiel
|           | $a$       | $a$ | $\bar{a}$ | $\bar{a}$ |
| --------- | --------- | --- | --------- | --------- |
| $b$       | 1         |     |           | 1         |
| $\bar{b}$ |           |     |           |           |
|           | $\bar{c}$ | c   | c         | $\bar{c}$ |
$z = b \land \bar{c}$

# KV - Diagramm mit 4 Variablen

|           | $a$       | $a$ | $\bar{a}$ | $\bar{a}$ |           |
| --------- | --------- | --- | --------- | --------- | --------- |
| $b$       |           |     |           |           | $\bar{d}$ |
| $b$       |           |     |           |           | $d$       |
| $\bar{b}$ |           |     |           |           | $d$       |
| $\bar{b}$ |           |     |           |           | $\bar{d}$ |
|           | $\bar{c}$ | c   | c         | $\bar{c}$ |           |
Bündelungen dürfen mit 2, 4, 8 oder 16 benachbarten Vollkonjunktionen erfolgen. Felder der Außenseiten sind zueinander benachbart.

## Beispiel
|           | $a$       | $a$ | $\bar{a}$ | $\bar{a}$ |           |
| --------- | --------- | --- | --------- | --------- | --------- |
| $b$       | 1         |     |           | 1         | $\bar{d}$ |
| $b$       |           |     |           |           | $d$       |
| $\bar{b}$ |           |     |           |           | $d$       |
| $\bar{b}$ | 1         |     |           | 1         | $\bar{d}$ |
|           | $\bar{c}$ | c   | c         | $\bar{c}$ |           |
$z = (a \land b \land \bar{c} \land \bar{d}) \lor (\bar{a} \land b \land \bar{c} \land \bar{d}) \lor (\bar{a} \land \bar{b} \land \bar{c} \land \bar{d})$
$z = \bar{c} \land \bar{d}$

## Beispiel 2
Eine Verknüpfungsschaltung soll nach Vorgaben folgende Wahrheitstabelle erfüllen

| d   | c   | b   | a   | z   |
| --- | --- | --- | --- | --- |
| 0   | 0   | 0   | 0   | 0   |
| 0   | 0   | 0   | 1   | 0   |
| 0   | 0   | 1   | 0   | 0   |
| 0   | 0   | 1   | 1   | 0   |
| 0   | 1   | 0   | 0   | 1   |
| 0   | 1   | 0   | 1   | 1   |
| 0   | 1   | 1   | 0   | 1   |
| 0   | 1   | 1   | 1   | 1   |
| 1   | 0   | 0   | 0   | 0   |
| 1   | 0   | 0   | 1   | 0   |
| 1   | 0   | 1   | 0   | 0   |
| 1   | 0   | 1   | 1   | 0   |
| 1   | 1   | 0   | 0   | 1   |
| 1   | 1   | 0   | 1   | 0   |
| 1   | 1   | 1   | 0   | 1   |
| 1   | 1   | 1   | 1   | 0   |
ges.:
a) KDNF

$(\bar{a} \land \bar{b} \land c \land \bar{d}) \lor (a \land \bar{b} \land c \land \bar{d}) \lor (\bar{a} \land b \land c \land \bar{d}) \lor (a \land b \land c \land \bar{d}) \lor (\bar{a} \land \bar{b} \land c \land d) \lor (\bar{a} \land b \land c \land d)$ 

b) Vereinfachung mit einem KV-Diagramm


|           | $a$       | $a$ | $\bar{a}$ | $\bar{a}$ |           |
| --------- | --------- | --- | --------- | --------- | --------- |
| $b$       |           | 1   | 1         |           | $\bar{d}$ |
| $b$       |           |     | 1         |           | $d$       |
| $\bar{b}$ |           |     | 1         |           | $d$       |
| $\bar{b}$ |           | 1   | 1         |           | $\bar{d}$ |
|           | $\bar{c}$ | c   | c         | $\bar{c}$ |           |


c) Verknüpfungsschaltung skizzieren

![[KV - Diagramme 03-04-25 12.06.40.excalidraw]]
