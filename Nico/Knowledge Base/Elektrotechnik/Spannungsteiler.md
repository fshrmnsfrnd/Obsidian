---
tags:
Fach:
Thema:
  - "[[Elektrotechnik]]"
---
## Spannungsteiler
Ein Spannungsteiler wird verwendet um von einem Widerstand Spannung zu nehmen. Hierfür wird ein zweiter Widerstand parallel zum zu mindernden eingeführt

#### Verhältnisse
$\frac{U_1}{U_2} = \frac{R_1}{R_2}$
$\frac{U_1}{U_{ges}} = \frac{R_1}{R_{ges}}$
$\frac{U_2}{U_{ges}} = \frac{R_2}{R_{ges}}$

### Der unbelastete Spannungsteiler

Der unbelastete Spannungsteiler lässt sich über die [[#Verhältnisse]] bestimmen.

![[Spannungsteiler 2024-11-17 13.54.35.excalidraw]]

[[Die Knotenpunkt- und Maschenregel#Maschenregel (2. Kirchhoffsche Regel)|Maschenregel]]
$U_1 = U - U_2$
$U_1 = 60V - 35V$

$\frac{U_1}{U_2} = \frac{R_1}{R_2}$ 
$\frac{25V}{35V} = \frac{10k\ohm}{R_2}$
$R_2 = 10k\ohm / \frac{25V}{35V}$
$R_2 = 14k\ohm$

### Der belastete Spannungsteiler

![[Pasted image 20241105234346.png]]

#### Möglichkeit 1
Der Spannungsteiler kann entweder über die [[#Verhältnisse|Verhältnisse]] berechnet werden.

$R_{2L} = \frac{1}{\frac{1}{55} + \frac{1}{60}} = 28,696 \ohm$
$R_{ges} = R_{2L} + R_1 = 120 \ohm$
$\frac{U_2}{U} = \frac{R_{2L}}{R_{ges}} | *U$ 
$U_2 = 44,39 V$

#### Möglichkeit 2
Oder mithilfe des [[Der elektrische Widerstand#Das magische Dreieck|Magischen Dreiecks]] berechnet werden

$R_{2L} = \frac{1}{\frac{1}{55} + \frac{1}{60}} = 28,696 \ohm$
$R_{ges} = R_{2L} + R_1 = 120 \ohm$
$I_1 = \frac{U}{R_{ges}} = \frac{230V}{148,696} = 1,546A$
$U_2 = I_1 * R_{R2L} = 44,386V*$
