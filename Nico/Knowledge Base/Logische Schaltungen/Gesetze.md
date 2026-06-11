---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---
# Kommutativgesetz (Vertauschungsgesetz)
Vertauschung von Variablen innerhalb einer Verknüpfungsart
![[Kommutativgesetz (Vertauschungsgesetz) 13-02-25 13.06.01.excalidraw]]

# Assoziativgesetz (Verknüpfungsgesetz)
Beliebige Wahl der Reihenfolge von Einzelverknüpfungen innerhalb einer Verknüpfungsart.

$(a \land b) \land c = a \land (b \land c)$
$(a \lor b) \lor c = a \lor (b \lor c)$
$(a * b) * c = a * (b * c)$

# Distributivgesetz (Verteilungsgesetz / Ausklammern)
![[Gesetze 18-02-25 12.11.05.excalidraw]]


> [!WARNING] Achtung
> Das Ausklammern von Summanden ist in der Mathematik NICHT erlaubt. In der [[Schaltalgebra]] ist das Ausklammern von ODER-[[Verknüpfungen]] jedoch erlaubt


# De-Morgansche Regeln

| $z = \overline{a \land b} = \overline{a} \lor \overline{b}$
|| $z = \overline{a \lor b} = \overline{a} \land \overline{b}$

## Überprüfung der Wahrheitstabelle

| b   | a   | $\overline{b}$ | $\overline{a}$ | $a \land b$ | $\overline{a \land b}$ | $\overline{a} \lor \overline{b}$ | $a \lor b$ | $\overline{a \lor b}$ | $\overline{a} \land \overline{b}$ |
| --- | --- | -------------- | -------------- | ----------- | ---------------------- | -------------------------------- | ---------- | --------------------- | --------------------------------- |
| 0   | 0   | 1              | 1              | 0           | 1                      | 1                                | 0          | 1                     | 1                                 |
| 0   | 1   | 1              | 0              | 0           | 1                      | 1                                | 1          | 0                     | 0                                 |
| 1   | 0   | 0              | 1              | 0           | 1                      | 1                                | 1          | 0                     | 0                                 |
| 1   | 1   | 0              | 0              | 1           | 0                      | 0                                | 1          | 0                     | 0                                 |

$z = \overline{a \land b \land c \land d ...} = \overline{a} \lor \overline{b} \lor \overline{c} \lor \overline{d} ...$
$z = \overline{a \lor b \lor c \lor d ...} = \overline{a} \land \overline{b} \land \overline{c} \land \overline{d}...$

$z = a \land b = \overline{\overline{a \land b}} = \overline{\overline{a} \lor \overline{b}} = \overline{\overline{a}} \land \overline{\overline{b}} = a \land b$ 
$z = a \lor b = \overline{\overline{a \lor b}} = \overline{\overline{a} \land \overline{b}} = \overline{\overline{a}} \lor \overline{\overline{b}} = a \lor b$ 

# Übung
Gilt $(a \land b) \lor c \ne  a \land (b \lor c)$

| c   | b   | a   | $a \land b$ | $b \lor c$ | $(a \land b) \lor c$ | $\ne$ | $a \land (b \lor c)$ |
| --- | --- | --- | ----------- | ---------- | -------------------- | ----- | -------------------- |
| 0   | 0   | 0   | 0           | 0          | 0                    |       | 0                    |
| 0   | 0   | 1   | 0           | 0          | 0                    |       | 0                    |
| 0   | 1   | 0   | 0           | 1          | 0                    |       | 0                    |
| 0   | 1   | 1   | 1           | 1          | 1                    |       | 1                    |
| 1   | 0   | 0   | 0           | 1          | 1                    | $\ne$ | 0                    |
| 1   | 0   | 1   | 0           | 1          | 1                    |       | 1                    |
| 1   | 1   | 0   | 0           | 1          | 1                    | $\ne$ | 0                    |
| 1   | 1   | 1   | 1           | 1          | 1                    |       | 1                    |
