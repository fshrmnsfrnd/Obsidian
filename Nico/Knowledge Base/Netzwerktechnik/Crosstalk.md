---
tags:
Fach:
Thema:
  - "[[Elektrotechnik]]"
---
# Crosstalk, NEXT, FEXT, Alien Crosstalk
---
>Leitungen die über lange Strecken nebeneinanderliegen, beeinflussen sich gegenseitig.

Die Leitungskopplung entsteht durch:
1. Kopplung der Isolationswiderstände
2. Kapazitive Kopplung zwischen den Leitern
3. Induktive Kopplung (magnetische Felder)
![[Der Wellenwiderstand in der Hochfequenzbetrachtung 30-09-25 14.35.54.excalidraw]]
## NEXT (Near End Crosstalk)
---
Ein Signal wird am Ende A in Leitung 1 eingespeist. Wird das Signal in Leitung 2 am gleichen Ende A gemessen, das durch Einstreuung von Leitung 1 dort entsteht, nennt man dies NEXT (Nahnebensprechdämpfung)
$$
a_{NEXT} = 10 * log(\frac{P_1}{P_3}) dB = 20 * log(\frac{U_1}{U_3}) dB
$$

## FEXT (Far End Cross Talk)
---
Wird das Signal gemessen, das durch Einstreuung von Leitung 1 am Ende B von Leitung 2 entsteht so nennt man dies FEXT (Fernnebensprechdämpfung)
$$
a_{FEXT} = 10 * log(\frac{P_1}{P_4}) dB = 20 * log(\frac{U_1}{U_4}) dB
$$

$$
a_{NEXT} < a_{FEXT}
$$

## Alien-Crosstalk 
---
Übersprechen von Leitungen außerhalb des eigenen Kabels

