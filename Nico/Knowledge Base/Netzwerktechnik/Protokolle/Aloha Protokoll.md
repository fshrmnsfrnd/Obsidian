---
Fach:
Thema:
  - "[[Networks]]"
---
# Exemplarische Darstellung einer erfolgreichen Übertragung
![[Erfolgreiche Übertragung 2025-10-09 14.24.35.excalidraw 1]]

Übertragung mit Fehler:
![[Erfolgreiche Übertragung 2025-10-09 14.40.29.excalidraw]]


Beim ursprünglichen ALOHA-Protokoll konnten Terminals Datenrahmen zu beliebigen Zeiten versenden.
z.B:
![[Erfolgreiche Übertragung 2025-10-09 15.00.31.excalidraw]]

# Effizienz von ALOHA
-> d.h. Wie hoch ist der Anteil der Rahmen, die unbeschadet bzw. kollisionsfrei übertragen werden können.

## Definitionen
$t_ü$ = Übertragungszeit(eines Rahmens) fester Länge
$t_ü = \frac{Rahmenlänge in Bit}{Bitrate in \frac{Bit}{S}}$
$N$ = Anzahl der Rahmen, die fortwährend in jedem Zeitfenster $t_ü$ von allen Stationen versendet werden.
Wenn $N > 1$ , wird mehr als ein Rahmen in jedem Zeitfenster $t_ü$ versendet und es käme fortwährend zu Kollisionen. 
>[!Note] **Daraus folgt:**
>$0 < N < 1$
>für einen gewissen Anteil an kollisionsfreien Übertragungen

G = N + diejenigen Rahmen, die aufgrund von Kollisionen wiederholt versendet werden
$$
G \ge N
$$
> [!NOTE] G = Anzahl der Sendeversuche pro $t_ü$


$P_0$ = Wahrscheinlichkeit, dass ein versendeter Datenrahmen Kollisionsfrei übertragen wird
$S$ = Durchsatz (erfolgreich übertragene Rahmen pro $t_ü$)
> [!NOTE] Es gilt
> $$
> S = G * P_0
> $$

# Betrachtung des Kollisionsintervalls eines Rahmens
Erinnerung: *Wenn ein Rahmen auf den Funkkanal gegeben wird, wird in ALOHA **nicht** vorher abgehört, um zu prüfen ob der Kanal frei ist.*

 Der Zugriff erfolgt willkürlich zu jedem Zeitpunkt

1. Wenn der Kanal bereits belegt ist, dann mindestens für den Zeitraum $t_ü$
2. Wird ein Rahmen versendet, dann wird der Kanal für $t_ü$ belegt.

Daraus folgt:
## 2 Kollisionsfälle
![[Aloha Protokoll 2025-10-14 14.18.30.excalidraw]] 

> Ein Kollisionsintervall besteht für die Dauer $2*t_ü$ 

**Begründung:**
Ein Rahman kann mit einem vorangegangenen Rahmen und einem nachfolgenden Rahmen kollidieren. Beide Rahmen belegen den Kanal jeweils für die Zeit $t_ü$ .

Die Wahrscheinlichkeit, dass $k$ Rahmen in einem Zeit Intervall versendet werden, ist dem bereits $G$ versendet werden, berechnet sich als:
$$
P_r(k) = \frac{G^K * e^{-G}}{k!}
$$
Die Wahrscheinlichkeit, dass $k=0$ Rahmen zusätzlich versendet werden müssen (d.h. Kollisionsfreiheit)
$$
P_r(0) = \frac{G^O*e^{-G}}{O!} = e^{-G}
$$
Da das Kollisionsintervall im klassischen ALOHA **$2 t_ü$** beträgt und es $G$ Versuche pro $t_ü$ gibt, müssen $2*G$ Versuche berücksichtigt werden.

Die Wahrscheinlichkeit, dass $k = O$ zusätzliche Senderahmen in einem $2*t_ü$ Zeitfenster versendet werden beträgt:
$$
P_O = P_r(0) = \frac{(2*G)^O*e^{-2G}}{O!} = e^{-2G}
$$

Durchsatz mit $S = G * P_0$ (siehe oben)
$$
S = G*e^{-2G}
$$
# Slotted ALOHA
>Damit kann der Durchsatz verbessert werden.

![[Aloha Protokoll 2025-10-16 14.25.39.excalidraw]]