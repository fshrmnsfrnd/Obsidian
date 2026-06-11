---
Fach:
tags:
Thema:
  - "[[Elektrotechnik]]"
---
![[Gemischte Schaltung 2024-11-17 14.33.12.excalidraw]]

### 1. Gesamtwiderstand mit Zwischenschritten

$R_{23} = \frac{1}{\frac{1}{R_2}+\frac{1}{R_3}} = 5k\ohm$ 
$R_{123} = R_1 + R_{23} = 10k\ohm$
$R_{1234} = \frac{1}{\frac{1}{R_4}+\frac{1}{R_{123}}} = 5k\ohm$
$R_{ges} = R_{12345} = R_5 + R_{1234} = 5k\ohm$

### 2. Gesamtstrom
$I_{ges} = U_{ges} / R_{ges} = 0,0008A = 0,8mA$

### 3. Rest berechnen

#### Spannungen

$U_5 = I_{ges} * R_5 = 16V$

$U_4 = I_{ges} * R_{1234} = 4V$

$U_1 = I_{123} * R_1 = 2V$

$U_2 = U_4 - U_1 = 2V$


#### Ströme

$I_4 = U_4 / R_4 = 0,0008A = 0,8mA$

$I_{123} = I_{ges} - I_4$ = $0,4mA$

$I_2 = U_2 / R_2 = 0,2mA$
