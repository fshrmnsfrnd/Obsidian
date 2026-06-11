---
Thema:
  - "[[Neural Networks]]"
---
Dabei wird versucht durch Annäherung möglichst nah ein ein **Minimum** zu gelangen, dafür wird die **[[Knowledge Base/KI/Neural Networks/Fehlerfunktion|Fehlerfunktion]]** möglichst weit Reduziert:  
$$
x_{neu}=x_{alt}−η∗∇f(x_{alt})
$$
- `f(x)` ist die **[[Knowledge Base/KI/Neural Networks/Fehlerfunktion|Fehlerfunktion]]**  
- `x` ist der **Parameter** (z. B. Gewicht im Neuron)  
- `η` ist die **Lernrate**

![[Pasted image 20260310122555.png]]

Wie viele Schritte wir gehen wird über den Hyperparameter **Iterationen** festgelegt.  
-> zu **klein** gewählt kommen wir nicht nah genug an das Minimum  
-> zu **groß** gewählt kann es sein das wir über das Minimum hinaus gehen oder Rechenleistung verschwenden  

> [!NOTE] In der Praxis wird meist eine **Abbruchbedingung** eingebaut das z. B. wenn der Fehler kleiner als $10^{−6}$ ist, ist der Fehler akzeptabel  

Die **Lernrate** ($η$) muss auch gut gewählt sein:  
- ist sie zu **groß** kann es sein das man wieder im Graphen **Aufschwingt**
![[Pasted image 20260310123037.png]]

Ist er zu klein gewählt kann es sein das man über ein **Lokales Minima** nicht hinaus kommt und somit nie das **Globale Minima** erreicht.
![[Pasted image 20260310123150.png]]
**Sattelpunkte** sind für diese Algorithmen auch ein Problem. Auf Grund der abnehmenden Steigung kann es passieren das er mit einem **Minima** verwechselt wird.
![[Pasted image 20260310123203.png]]
