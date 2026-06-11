---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---
# Wahrheitstabelle

| Dez | $t^m$ |       |       |       | $t^{m+1}$ |       |       |       |
| --- | ----- | ----- | ----- | ----- | --------- | ----- | ----- | ----- |
|     | $q_a$ | $q_b$ | $q_c$ | $q_d$ | $q_a$     | $q_b$ | $q_c$ | $q_d$ |
| 0   | 1     | 0     | 0     | 1     | 0         | 0     | 0     | 0     |
| 1   | 0     | 0     | 0     | 0     | 0         | 0     | 0     | 1     |
| 2   | 0     | 0     | 0     | 1     | 0         | 0     | 1     | 0     |
| 3   | 0     | 0     | 1     | 0     | 0         | 0     | 1     | 1     |
| 4   | 0     | 0     | 1     | 1     | 0         | 1     | 0     | 0     |
| 5   | 0     | 1     | 0     | 0     | 0         | 1     | 0     | 1     |
| 6   | 0     | 1     | 0     | 1     | 0         | 1     | 1     | 0     |
| 7   | 0     | 1     | 1     | 0     | 0         | 1     | 1     | 1     |
| 8   | 0     | 1     | 1     | 1     | 1         | 0     | 0     | 0     |
| 9   | 1     | 0     | 0     | 0     | 1         | 0     | 0     | 1     |
# Anwendungsgleichung
$q_d^{m+1} = (q_a \land q_b \land q_b \land \overline{q_d}) \lor (\overline{q_a} \land \overline{q_b} \land \overline{q_c} \land q_d)$

# KV-Diagramm

|             | $q_a$       | $q_a$ | $\bar{q_a}$ | $\bar{q_a}$ |             |
| ----------- | ----------- | ----- | ----------- | ----------- | ----------- |
| $q_b$       |             | 1     |             |             | $\bar{q_d}$ |
| $q_b$       | x           | x     | x           | x           | $q_d$       |
| $\bar{q_b}$ |             | x     | x           | 1           | $q_d$       |
| $\bar{q_b}$ |             |       |             |             | $\bar{q_d}$ |
|             | $\bar{q_c}$ | $q_c$ | $q_c$       | $\bar{q_c}$ |             |
## Vereinfachte Anwendungsgleichung
$q_d = (q_a \land q_b \land q_b \land \overline{q_d}) \lor (q_d \land \overline{q_a})$

## Anwendungsgleichungen
1. $q^{m+1}_a = \overline{q_a}$
2. $q^{m+1}_b = (\overline{q_a} \land q_b) \lor (q_a \land \overline{q_b} \land \overline{q_d})$
3. $q^{m+1}_c = (\overline{q_a} \land q_c) \lor (q_c \land \overline{q_b}) \lor (q_a \land q_b \land \overline{q_c})$
4. $q^{m+1}_d = (\overline{q_a} \land q_d) \lor (q_a \land q_b \land q_c \land \overline{q_d})$ 

## Bestimmung der Verknüpfungsgleichung durch Vergleich charakteristischer Gleichung und Anwendungsgleichung

>j ist, wo $q$ ist und k ist wo $\bar{q}$ ist
### FF-A
**Charakteristische Gleichung:** $q_a^{m+1} = (j_a \land \overline{q_a}) \lor (\overline{k_a} \land q_a)$
**Anwendungsgleichung:** $q_a^{m+1} = \overline{q_a}$
=> 
$j_a = 1$ 
$\overline{k_a} = 0$
$k_a = 1$

### FF-B
**Charakteristische Gleichung:** $q_b^{m+1} = (j_b \land \overline{q_b}) \lor (\overline{k_b} \land q_b)$
**Anwendungsgleichung:** $q_b^{m+1} = (\overline{q_a} \land q_b) \lor (q_a \land \overline{q_b} \land \overline{q_d})$
=> $q_b^{m+1} = (q_a \land \overline{q_d} \land \overline{q_b}) \lor (\overline{q_a} \land q_b)$

### FF-C
$j_c = q_a \land q_b$
$k_c = q_a \land q_b$

### FF-D
$j_d = q_a \land q_b \land q_c$
$k_d = q_a$