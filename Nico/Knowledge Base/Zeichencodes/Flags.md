---
Fach:
tags:
Thema:
  - "[[Zeichencodes]]"
---
## Negativ-Flag (N-Flag)

signed 8-Bit: <span style="color: yellow">1</span>010 1011
Das <span style="color: yellow;">Vorzeichen-Bit</span> ist auf "1", also ist die Zahl negativ.

## Carry-Flag (C-Flag)

![[Flags 2024-11-11 22.55.34.excalidraw]]

<span style="color: yellow;">1</span>  = 1 im Statusregister

Wird gesetzt wenn ein Übertrag in das nächsthöhere Bit gesetzt wird

## Vorzeichen des wahren Ergebnisses (S-Flag)

S = [[#Overflow-Flag (V-Flag)|V]] [[#Antivalenz (XOR)|XOR]] [[#Negativ-Flag (N-Flag)|N]] 

## Overflow-Flag (V-Flag)

>gilt nur für "signed" Zahlen

"Carry in"  => Carry Bit (Übertrags Bit) **in** die Vorzeichenstelle
"Carry out" => Carry Bit (Übertrags Bit) **aus** der Vorzeichenstelle heraus nehmen

V = Carry in [[#Antivalenz (XOR)|XOR]] Carry out

Ist das `V-Flag = 1`, ist das Ergebnis ungültig.

![[Pasted image 20241111231816.png]]


## Zero-Flag (Z-Flag)

Ist das Ergebnis "0" wird das Z-Flag auf "1" gesetzt.

## Antivalenz (XOR)

![[Pasted image 20241111231409.png]]

## Alle Flags zusammen:

![[Flags 2024-11-11 23.47.55.excalidraw]]