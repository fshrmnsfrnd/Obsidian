---
Thema:
  - "[[Vektorrechnung]]"
Fach: "[[Mathe]]"
---
![[Pasted image 20260113174523.png]]
$$
E: \vec{x} = \vec{a} + r * \vec{u} + s * \vec{v}
$$
$$
E: \vec{x} = \vec{Aufpunkt} + LangeGerade1 * \vec{Gerade1} + LangeGerade2 * \vec{Gerade2}
$$
# Aufstellen aus 3 Punkten
A(3|0|0) B(0|3|0) C(0|0|3)
$\vec{AB} = \left(\begin{array}{c} -3\\ 3\\ 0\\ \end{array}\right)$ $\vec{AC} = \left(\begin{array}{c} -3\\ 0\\ 3\\ \end{array}\right)$
$$
E: \vec{x} = \vec{A} + r * \vec{AB} + s * \vec{AC}
$$
$$
E: \vec{x} = \left(\begin{array}{c} 3\\ 0\\ 0\\ \end{array}\right) + r * \left(\begin{array}{c} -3\\ 3\\ 0\\ \end{array}\right) + s * \left(\begin{array}{c} -3\\ 0\\ 3\\ \end{array}\right)
$$
# Aufstellen aus einer Geraden und einem Punkt der nicht auf der Geraden liegt

Ebenengleichung: Als Aufpunkt wählt man z.B. den Aufpunkt $A$ der Geraden $g$, als Richtungsvektoren z.B. den Richtungsvektoren $\vec{u}$ der Geraden und den Verbindungsvektor $\vec{AP}$

Gegeben:
P(0|0|3)
$g: \vec{x} = \left(\begin{array}{c} 3\\ 0\\ 0\\ \end{array}\right) + r * \left(\begin{array}{c} -1\\ 1\\ 0\\ \end{array}\right)$
Ebenengleichung:
$$
E: \vec{x} = \vec{A} + r * \vec{u} + s * \vec{AP}
$$
$$
E: \vec{x} = \left(\begin{array}{c} 3\\ 0\\ 0\\ \end{array}\right) + r * \left(\begin{array}{c} -1\\ 1\\ 0\\ \end{array}\right) + s * \left(\begin{array}{c} -3\\ 0\\ 3\\ \end{array}\right)
$$ 
# Aufstellen aus 2 echt parallelen Geraden

Ebenengleichung: Als Aufpunkt wählt man z.B. den Aufpunkt $A$ der Geraden $g$, als Richtungsvektoren z.B. den Richtungsvektoren $\vec{u}$ der Geraden und den Verbindungsvektor $\vec{AB}$, der die Aufpunkte der Geraden $g$ und $h$ miteinander verbindet.

Gegeben:
$g: \vec{x} = \left(\begin{array}{c} 1\\ 2\\ 3\\ \end{array}\right) + r * \left(\begin{array}{c} 1\\ 1\\ 1\\ \end{array}\right)$ $h: \vec{x} = \left(\begin{array}{c} 0\\ 0\\ 1\\ \end{array}\right) + s * \left(\begin{array}{c} 2\\ 2\\ 2\\ \end{array}\right)$
Ebenengleichung:
$$
E: \vec{x} = \vec{A} + r * \vec{u} + s * \vec{AB}
$$
$$
E: \vec{x} = \left(\begin{array}{c} 1\\ 2\\ 3\\ \end{array}\right) + r * \left(\begin{array}{c} 1\\ 1\\ 1\\ \end{array}\right) + s * \left(\begin{array}{c} -1\\ -2\\ -2\\ \end{array}\right)
$$ 
# Aufstellen aus 2 sich schneidenden Geraden

Ebenengleichung: Als Aufpunkt wählt man z.B. den Aufpunkt $A$ der Geraden $g$, als Richtungsvektoren am besten gleich die Geraden

Gegeben:
$g: \vec{x} = \left(\begin{array}{c} 7\\ -2\\ 2\\ \end{array}\right) + r * \left(\begin{array}{c} 2\\ 3\\ 1\\ \end{array}\right)$ $h: \vec{x} = \left(\begin{array}{c} 4\\ -6\\ -1\\ \end{array}\right) + s * \left(\begin{array}{c} 1\\ 1\\ 2\\ \end{array}\right)$
Ebenengleichung:
$$
E: \vec{x} = \vec{a} + r * \vec{u} + s * \vec{v}
$$
$$
E: \vec{x} = \left(\begin{array}{c} 7\\ -2\\ 2\\ \end{array}\right) + r * \left(\begin{array}{c} 1\\ 1\\ 2\\ \end{array}\right) + s * \left(\begin{array}{c} 2\\ 3\\ 1\\ \end{array}\right)
$$ 
# Prüfen ob 2 Geraden eine Ebene bilden
---
>2 Geraden bilden eine Ebene wenn sie parallel sind oder sich schneiden

Gegeben:
$g: \vec{x} = \left(\begin{array}{c} 7\\ -2\\ 2\\ \end{array}\right) + r * \left(\begin{array}{c} 2\\ 3\\ 1\\ \end{array}\right)$ $h: \vec{x} = \left(\begin{array}{c} 4\\ -6\\ -1\\ \end{array}\right) + s * \left(\begin{array}{c} 1\\ 1\\ 2\\ \end{array}\right)$
