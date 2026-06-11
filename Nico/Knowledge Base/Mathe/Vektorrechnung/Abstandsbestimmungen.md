---
Fach: "[[Mathe]]"
Thema:
  - "[[Vektorrechnung]]"
---
# 1. Fall: Punkt - Punkt
---
Der Abstand ist gleich dem Betrag des Verbindungsvektors der Punkte
### Beispiel
$P(6|3), Q(1|2)$
$\vec{PQ} = \left(\begin{array}{c} -5\\ -1\\ \end{array}\right)$ 
$$
\sqrt{(-5)^2+(-1)^2} = 5,1LE
$$
# 2. Fall: Punkt - Gerade
---
Der Abstand ist gleich der Länge des Lotes von Gerade und Punkt
**Vorgehen**
1. Aufstellen einer Gleichung einer Ebene die den Punkt enthält und senkrecht zur Geraden ist
	- Ortsvektor der Gerade wird zum Normalenvektor der Ebene (Dadurch senkrecht)
	- Der Punkt wird Aufpunkt der Ebene
2. Bestimmen des Schnittpunktes der Ebene und der Geraden
	- Gerade in die Koordinatenform der Ebene einsetzen
	- Die obere Zeile der Geradengleichung (also $a_1 + r u_1$) wird zu  $x_1$ , die zweite zu $x_2$ usw.
3. Berechnen des Abstandes zwischen dem Schnittpunkt und dem Punkt
### Beispiel
$P(6|7|-3)$
$g:\vec{X}=\left(\begin{array}{c} 2\\ 1\\ 4\\ \end{array}\right) + r * \left(\begin{array}{c} 3\\ 0\\ -2\\ \end{array}\right)$ 
#### Ebene, die $P$ enthält und auf der $g$ senkrecht steht
$$
E: \left(\begin{array}{c} 3\\ 0\\ -2\\ \end{array}\right) \circ \left(\vec{x} - \left(\begin{array}{c} 6\\ 7\\ -3\\ \end{array}\right)\right) = 0
$$
$$
E: 3x_1-2x_3-24=0
$$
#### Schnittpunkt berechnen
$$
g \cap E: 3 * (2+3r)-2*(4-2r)-24=0
$$
$r = 2$
$$
F=(8|1|0)
$$
#### Abstand berechnen
$\vec{PF}=\left(\begin{array}{c} 2\\ -6\\ 3\\ \end{array}\right)$ 
$$
d(P;g)=|\vec{PF}| = \sqrt{2^2+6^2+3^2}=7LE
$$
# 3 Fall: Punkt - Ebene
---
Es muss die Hesse Normalenform vorliegen

> [!NOTE] Hesse Normalenform
> Um die Hesse Normalenform aufzustellen, dividiert man den Vektor in Normalenform durch den Betrag des Normalenvektors $|\vec n|$
> $$
> \frac{n_1x_1+n_2x_2+n_3x_3+d}{\sqrt{(n_1)^2+(n_2)^2+(n_3)^2}}=0
$$

Den Abstand eines Punktes $P$ zur Ebene erhält man durch einsetzen in die Hesse Normalform ($P(p_1|p_2|p_3)$ als $x_1,x_2,x_3$)
### Beispiel
$P(2|0|2)$
$E: \left(\begin{array}{c} 2\\ -1\\ 2\\ \end{array}\right) \circ \left(\vec{x} - \left(\begin{array}{c} 3\\ 5\\ -1\\ \end{array}\right)\right)=0$ 
#### Normalenvektor von $E$
$$
E: 3x_1-x_2+2x_3+1=0
$$

#### HNF von $E$
$$
\frac{2x_1-x_2+2x_3+1}{\sqrt{2^2+1^2+2^2}}=0, \frac{2x_1-x_2+2x_3+1}{3}=0
$$
$$
d(A;E) = | \frac{2*2-0+2*2+1}{3}| = 3LE
$$
# Weitere darauf zurückführbare Fälle
---
## Gerade - Gerade
Man nimmt einen beliebigen Punkt auf der einen Gerade und berechnet wie beim 2. Fall den Abstand zur anderen Gerade
## Zwei parallele Ebenen
Man nimmt einen beliebigen Punkt auf der einen Ebene und berechnet wie beim 3. Fall den Abstand zur anderen Ebene
## Ebene - parallele Gerade
Man nimmt einen beliebigen Punkt auf der Gerade und berechnet wie beim 3. Fall den Abstand zur Ebene

