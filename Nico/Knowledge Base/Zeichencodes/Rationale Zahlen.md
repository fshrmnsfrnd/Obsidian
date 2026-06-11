---
Fach:
tags:
Thema:
  - "[[Zeichencodes]]"
---
## Festkommaformat

Ein Rechenwerk mit n-Bitstellen kann unterteilt werden in einen Teil für Vorkommastellen und einen anderen Teil für Nachkommastellen.

**Beispiel:** 8-Bit Rechenwerk  
Vorkommastellen: 3  
Nachkommastellen: 4
![[Pasted image 20241112001739.png]]

**Vorteil:** Jedes Rechenwerk, das mit ganzen Zahlen Rechenoperationen durchführen kann, kann auch für Festkommaoperationen verwendet werden.
**Nachteil:** Eingeschränkter Wertebereich
   -> kleine Zahlen gehen durch Runden verloren.  
   -> große Zahlen können nicht mehr dargestellt werden.  
  
=> Einsatz: Digitale Signalprozessoren.

### Äquidistanz
Dies ist der kleinstmögliche Abstand zwischen zwei benachbarten Zahlen. (Bei Festkommazahlen Konstant)
signed:
$2^{-(n-1)}$ 
unsigned:
$2^{-n}$ 
>Für $n$  = 8, signed: $2^{-7}$

## Gleitkommazahlen (Nach IEEE 754)

**IEEE 754 legt zwei Formate fest:**
-> single precision, 32-Bit (einfache Genauigkeit)  
-> double precision, 64-Bit (doppelte Genauigkeit)
in C/Java entspricht dies den Datentypen **float** und **double**.

![[Pasted image 20241112003136.png]]

### Vorgehen zur Bestimmung des IEEE - Formats (32 Bit)

1. Berechnung der Binären [[Zahlensysteme#Allgemeines Schema für Stellenwertsysteme|Vor]]- und [[Zahlensysteme#Restwertverfahren für Zahlen zwischen 0 und 1|Nach]]kommastellen
	z. B. $15,625_{(10)} = 1111,101_{(2)}$ 
	
2. Verschieben des Kommas hinter die werthöchste Stelle
	1,111101∗2$^3$ => Exponent E=3
	
3. Mantisse bilden:
	Das werthöchste Bit wird "versteckt" d.h. implizit dargestellt und die verbleibende Ziffernfolge mit Nullen aufgefüllt bis 23 Bit (Länge der Mantisse)!
	111 1101 => 111 1010 0000 0000 0000 0000
	
4. Charakteristik bilden:
	C=E+V oder Charakteristik = Exponent + Verschiebezahl  
		V=127$_{(10)}​$ bei 8-Bit Charakteristik  
		V=1023$_{(10)}​$​ bei 11-Bit Charakteristik  
	C=3+127=130$_{(10)}​$=1000 0010$_{(2)}​$
	
5. Vorzeichenbit der IEEE Zahl:
	0 = +
	1 = −
	
6. **Kombinieren zur IEEE Zahl**:
	![[Pasted image 20241112004757.png]]

### Beispiel
![[Pasted image 20241112005157.png]]
