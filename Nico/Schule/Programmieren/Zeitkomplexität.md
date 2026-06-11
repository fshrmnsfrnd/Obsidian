---
Fach: "[[Programmieren]]"
---
>Von einer theoretisch berechneten Laufzeit $4n^7 +3n^3 +5$ ist nur $4n^7$ relevant. 
Das bedeutet unter anderem, dass nur Schleifen und rekursive Aufrufe betrachtet werden müssen. Aus der exakten Laufzeit $4n^7 +3n^3 + 5$ wird also ungefähr $n^7$ . 
Dafür gibt es die kurze Schreibweise $O(n^7)$. 

**Beispiele:**
- Ein Algorithmus benötigt unabhängig von der Eingabe fünf Operationen: $O(1)$ 
- Ein Algorithmus benötigt für $n$ Eingaben $n + 3$ Operationen: $O(n)$
- Ein Algorithmus benötigt für $n$ Eingaben $n2 + 17$ Operationen: $O(n^2)$ 
- Eine Schleife läuft $n^2$ -mal und danach eine zweite Schleife n-mal $O(n^2)$ 
- Drei mal so viele Eingaben brauchen etwa 27 mal so viel Zeit $O(n^3)$

**Synonyme:** 

| Notation    | Beschreibung            |
| ----------- | ----------------------- |
| $O(1)$      | konstante Laufzeit      |
| $O(log(n))$ | logarithmische Laufzeit |
| $O(n)$      | lineare Laufzeit        |
| $O(n^2)$    | quadratische Laufzeit   |
![[Pasted image 20251204091251.png]]
