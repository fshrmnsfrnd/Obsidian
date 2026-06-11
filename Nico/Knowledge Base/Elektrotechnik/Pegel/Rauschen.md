---
tags:
Fach:
Thema:
  - "[[Elektrotechnik]]"
---
# Rauschzahl $F$

Wenn man das [[Pegelabstand|Signal-Rausch-Verhältnis]] ($SNR$) vom Eingang mit dem vom Ausgang ins Verhältnis setzt erhält man die **Rauschzahl F**.  

mit Größen (Ergebnis ohne Einheit): 
$F = \frac{SNR_{ein}}{SNR_{aus}}$

$= \frac{P_{ein,Signal} / P_{ein,Rauschen}} {P_{aus,Signal} / P_{aus,Rauschen}}$ 

$= \frac{(U_{ein,Signal} / U_{ein,Rauschen})^2}{(U_{aus,Signal} / U_{aus,Rauschen})^2}$

 mit Pegel (Ergebnis in dB):  
 $F_{dB} = 10 ∗ log⁡(\frac{SNR_{ein}}{SNR_{aus}}) = 10 * log(F)$
 $F = 10^{L / 10}$
## Verkettung
2 Kettenglieder: $F_1 + \frac{F_2 - 1}{G_1}$ 
3 Kettenglieder: $F_1 + \frac{F_2 - 1}{G_1} + \frac{F_3 - 1}{G_1 * G_2}$
usw. 

$G$ ist das selbe wie [[Verstärkungsmaß#Erklärung|L]]  