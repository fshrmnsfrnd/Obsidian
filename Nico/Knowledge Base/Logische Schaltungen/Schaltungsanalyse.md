---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---
- Digitalschaltungen bestehen (meist) aus vielen logischen Verknüpfungsgliedern
- Schaltungsanalyse ist die Ermittlung der Funktionsgleichung aus einer Gesamtschaltung

## Bsp.:
![[Schaltungsanalyse 04-02-25 08.59.13.excalidraw]]

Z Ausgangszustand
x, y: Ausgangszustände sowie Eingangszustände des Folgeglieds.
a, b Eingangszustände

**Zustandskombinationen:**

$2^2$ = 4

|     | b   | a   | x = $\overline{a}$ | y = x $\land$ b | z = $\overline{y}$ |
| --- | --- | --- | ------------------ | --------------- | ------------------ |
| 0   | 0   | 0   | 1                  | 0               | 1                  |
| 1   | 0   | 1   | 0                  | 0               | 1                  |
| 2   | 1   | 0   | 1                  | 0               | 0                  |
| 3   | 1   | 1   | 0                  | 1               | 1                  |

z = $\overline{y}$ 
y = x $\land$ B
x = $\overline{A}$ 

y = $\overline{A} \land B$   | x in y einsetzen
z = $\overline{\overline{A} \land B}$   | y in z einsetzen

## Übung

![[Schaltungsanalyse 04-02-25 09.16.41.excalidraw]]


|     | c   | b   | a   | u = $\overline{a}$ | v = $\overline{b}$ | t = u $\lor$ v | w = t $\lor$ c | x = b $\land$ c | y = $\overline{x}$ | z =w $\land$ y |
| --- | --- | --- | --- | ------------------ | ------------------ | -------------- | -------------- | --------------- | ------------------ | -------------- |
| 0   | 0   | 0   | 0   | 1                  | 1                  | 1              | 1              | 0               | 1                  | 1              |
| 1   | 0   | 0   | 1   | 0                  | 1                  | 1              | 1              | 0               | 1                  | 1              |
| 2   | 0   | 1   | 0   | 1                  | 0                  | 1              | 1              | 0               | 1                  | 1              |
| 3   | 0   | 1   | 1   | 0                  | 0                  | 0              | 0              | 0               | 1                  | 0              |
| 4   | 1   | 0   | 0   | 1                  | 1                  | 1              | 1              | 0               | 1                  | 1              |
| 5   | 1   | 0   | 1   | 0                  | 1                  | 1              | 1              | 0               | 1                  | 1              |
| 6   | 1   | 1   | 0   | 1                  | 0                  | 1              | 1              | 1               | 0                  | 0              |
| 7   | 1   | 1   | 1   | 0                  | 0                  | 0              | 1              | 1               | 0                  | 0              |

z = w $\land$ y
z = (t $\lor$ c)$\land$( $\overline{x}$)
z = (( u $\lor$  v) $\lor$ c) $\land$ $\overline{(b \land c)}$ 
z = (( $\overline{a}$ $\lor$  $\overline{b}$) $\lor$ c) $\land$ $\overline{(b \land c)}$ 

>Dies ist die ==Funktionsgleichung== der Schaltung. In Funktionsgleichungen treten nur Eingangsgrößen, und deren Negation auf. Sie können auch ohne Wahrheitstabelle direkt aus der Schaltung abgelesen werden

## Beispiel
![[Schaltungsanalyse 06-02-25 12.26.41.excalidraw]]

## Übung

![[Schaltungsanalyse 06-02-25 12.44.38.excalidraw]]

## Übung
Überprüfen Sie ob folgende Gleichungen jeweils einer XOR Verknüpfung entsprechen!
Erstellen Sie eine Wahrheitstabelle.

1. z = $\overline{(a \land b) \lor (\overline{a} \land \overline{b})}$ 


| b   | a   | a $\land$ b | $\overline{a} \land \overline{b}$ | (a $\land$ b) $\lor$ ($\overline{a} \land \overline{b}$) | $\overline{(a \land b) \lor (\overline{a} \land \overline{b})}$ |
| --- | --- | ----------- | --------------------------------- | -------------------------------------------------------- | --------------------------------------------------------------- |
| 0   | 0   | 0           | 1                                 | 1                                                        | 0                                                               |
| 0   | 1   | 0           | 0                                 | 0                                                        | 1                                                               |
| 1   | 0   | 0           | 0                                 | 0                                                        | 1                                                               |
| 1   | 1   | 1           | 0                                 | 1                                                        | 0                                                               |
2. z = (a $\lor$ b) $\land$ ($\overline{a} \lor \overline{b}$)

| a   | b   | a $\lor$ b | $\overline{a} \lor \overline{b}$ | (a $\lor$ b) $\land$ ($\overline{a} \lor \overline{b}$) |
| --- | --- | ---------- | -------------------------------- | ------------------------------------------------------- |
| 0   | 0   | 0          | 1                                | 0                                                       |
| 0   | 1   | 1          | 1                                | 1                                                       |
| 1   | 0   | 1          | 1                                | 1                                                       |
| 1   | 1   | 1          | 0                                | 0                                                       |

3.  z = (a $\land$ $\overline{b}$) $\lor$ ($\overline{a} \land b$)
 
| a   | b   | $\overline{a}$ | $\overline{b}$ | a $\land$ $\overline{b}$ | $\overline{a} \land b$ | (a $\land$ $\overline{b}$) $\lor$ ($\overline{a} \land b$) |
| --- | --- | -------------- | -------------- | ------------------------ | ---------------------- | ---------------------------------------------------------- |
| 0   | 0   | 1              | 1              | 0                        | 0                      | 0                                                          |
| 0   | 1   | 1              | 0              | 0                        | 1                      | 1                                                          |
| 1   | 0   | 0              | 1              | 1                        | 0                      | 1                                                          |
| 1   | 1   | 0              | 0              | 0                        | 0                      | 0                                                          |
4. z = $\overline{(a \lor \overline{b}) \land (\overline{a} \lor b)}$

| a   | b   | $\overline{a}$ | $\overline{b}$ | a $\lor$ $\overline{b}$ | $\overline{a} \lor b$ | $\overline{(a \lor \overline{b}) \land (\overline{a} \lor b)}$ |
| --- | --- | -------------- | -------------- | ----------------------- | --------------------- | -------------------------------------------------------------- |
| 0   | 0   | 1              | 1              | 1                       | 1                     | 0                                                              |
| 0   | 1   | 1              | 0              | 0                       | 1                     | 1                                                              |
| 1   | 0   | 0              | 1              | 1                       | 0                     | 1                                                              |
| 1   | 1   | 0              | 0              | 1                       | 1                     | 0                                                              |
