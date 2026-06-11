---
Fach:
tags:
Thema:
  - "[[Zeichencodes]]"
---
>CRC beruht auf Polynomdivision.
>Polynom: jeder Datenblock kann als Polynom gesehen werden
>Polynome sind $x^3+x^2+x^1$ 

$x^3+x^2+x^1$  hätte den Grad $G_{x}$  k = 3 

1. Anhängen von k Nullbits an die Datenfolge
2. Genaratorpolynom 1 0 1 1 ist gegeben  ![[Pasted image 20250119183915.png]]
3. Der Rest wird in die Nullbits eingeschrieben => 1 0 0 1 1 0 ==1 0 1
4. Der Empfänger besitzt das gleich Generatorpolynom und führt mit der Empfangenen Datenfolge die selbe Berechnung durch.
5. Ist der Rest beim Empfänger 0 war die Übertragung fehlerfrei

