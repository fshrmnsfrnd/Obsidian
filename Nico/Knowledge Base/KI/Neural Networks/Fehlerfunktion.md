---
Thema:
  - "[[Neural Networks]]"
---
Man bildet nun eine eigene Fehlerfunktion. D.h. eine Funktion die uns die Differenz zwischen dem vorhergesagten Wert und dem wahren Wert liefert. Die Funktion besitzt mehrere Parameter (Anzahl [[Neuronen]]). Es wird nun die Ableitung über die einzelnen Gewichte gebildet um entsprechend die Minima bestimmen zu können. Es gilt ein Numerische Problem zu lösen. Das Verfahren hierzu wird als Gradienten Abstieg (Gradient descent) bezeichnet.
**Gut gewählt Lernrate:**
![[Pasted image 20260304232544.png]]

**Zu große Lernrate:**
Wird die Lernrate n zu groß gewählt, kann dies zu einem Aufschwingen führen und die Berechnung der Gewichte ad absurdum führen.
![[Pasted image 20260304232623.png]]

**Zu kleine Lernrate**
Es gibt Mathematische Funktionen die mehrere Minima aufweisen. Hier spricht man von lokalen Minima und Globalen Minima.
Angenommen man würde die Suche nach dem Minimum der Fehlerfunktion in der Nähe des lokalen Minimums mit einer zu kleinen Lernrate beginnen. Dann kann es passieren, dass man nicht über das lokale Maximum hinauskommt und somit nicht das globale Minimum findet.
![[Pasted image 20260304232722.png]]
