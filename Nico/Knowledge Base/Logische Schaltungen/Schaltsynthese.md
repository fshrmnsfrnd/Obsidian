---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---
# Beispiel:
ein Förderkorb darf nur auffahren, wenn folgende Bedingungen erfüllt sind.

1. Die Ladeluke/Ladetüre muss geschlossen sein
2. max. zulässige Traglast darf nicht überschritten werden
3. Hebel zur Anfahrt muss betätigt werden

### 1.
a = 1 Türe ist geschlossen
a = 0 Türe ist offen

### 2.
b = 1 max Traglast ist nicht überschritten
b = 0 Traglast ist überschritten

### 3.
c = 1 Hebel ist an
c = 0 Hebel ist aus

z = 1 Förderkorb fährt
z = 0 Förderkorb fährt nicht

# Lösung nach der Kanonisch Disjunktiven Normalform (KDNF)

Mit der KDNF können [[Funktionsgleichungen]] in nicht minimierter Form aus einer Wahrheitstabelle ermittelt werden. 

Die KDNF besteht aus ODER [[Verknüpfungen]] von ==Vollkonjunktionen (Minterme).

Eine ==Vollkonjunktion== ist eine ==UND Verknüpfung==, in der alle Eingangsvariablen entweder negiert oder nicht negiert vorkommen. 
Bei ==zwei== Eingangsvariablen können ==vier== Vollkonjunktionen gebildet werden.

$a \land b$     $\overline{a} \land b$     $a \land \overline{b}$      $\overline{a} \land\overline{b}$

## Bestimmung der KDNF aus der Wahrheitstabelle
### Beispiel

| c   | b   | a   | z   |
| --- | --- | --- | --- |
| 0   | 0   | 0   | 0   |
| 0   | 0   | 1   | 0   |
| 0   | 1   | 0   | 0   |
| 0   | 1   | 1   | 0   |
| 1   | 0   | 0   | 0   |
| 1   | 0   | 1   | 0   |
| 1   | 1   | 0   | 0   |
| 1   | 1   | 1   | 1   |
=> Förderkopf fährt bei z = 1
=> $z = a \land b \land c$

![[Schaltsynthese 18-03-25 09.10.33.excalidraw]]

# Bestimmung der KDNF aus einer Wahrheitstabelle
 Beispiel: zwei Eingangsvariablen 

| Fälle | b   | a   | z   |
| ----- | --- | --- | --- |
| 0     | 0   | 0   | 1   |
| 1     | 0   | 1   | 0   |
| 2     | 1   | 0   | 1   |
| 3     | 1   | 1   | 0   |
> Fall 0 und Fall 2 ergeben am Ausgang z eine 1. Aus diesen Fällen werden die sogenannten Minterme bzw. Vollkonjunktionen gebildet.

Fall 0 => $\overline{a} \land \overline{b}$
Fall 2 => $\overline{a} \land b$

>z = $(\overline{a} \land \overline{b}) \lor (\overline{a} \land b)$ 

Die Funktionsgleichung, die diese Wahrheitstabelle erfüllt wird aus der ODER-Verknüpfung (Disjunktion) der Minterme gebildet.

Durch Vereinfachung:
$z = \overline{a} \land(\overline{b} \lor b) = \overline{a} \land 1 = \overline{a}$

# Übung
Gegeben ist folgende Wahrheitstabelle
a) Bestimmen Sie alle Minterme und die Funktionsgleichung in der KDNF
b) Entwerfen Sie die Verknüpfungsschaltung

| Fälle | c   | b   | a   | z   |
| ----- | --- | --- | --- | --- |
| 0     | 0   | 0   | 0   | 1   |
| 1     | 0   | 0   | 1   | 0   |
| 2     | 0   | 1   | 0   | 0   |
| 3     | 0   | 1   | 1   | 1   |
| 4     | 1   | 0   | 0   | 0   |
| 5     | 1   | 0   | 1   | 1   |
| 6     | 1   | 1   | 0   | 1   |
| 7     | 1   | 1   | 1   | 0   |
$z = (\bar{a} \land \bar{b} \land \bar{c}) \lor (\bar{a} \land b \land c) \lor (a \land \bar{b} \land c) \lor (a \land b \land \bar{c})$
