---
Fach:
tags:
Thema:
  - "[[Elektrotechnik]]"
---
Wenn kein Ein- und Ausgang vorliegt, wird die "Einheit" dB erweitert.
$1 dBm = 1mW$

# Pegel $L_P$ bzw. $L_U$ berechnen
Gegebenes $P$ bzw. $U$ in die Formel $L_P = 10 * log(\frac{P}{1 W}) dbW$ bzw. $L_U = 10 * log(\frac{U}{1 V}) dbW$einsetzen

# $P$ bzw. $U$ aus $L_P$ bzw. $L_U$ berechnen
Die entlogarithmierte Formel verwenden
$P = 10^{\frac{L_P}{10dbW}}$
$U = 10^{\frac{L_U}{20dbV}}$

>absoluter und relativer Pegel können in einer Kette addiert und subtrahiert werden:
>$6dBU + 20dB = 26dBU$ 

