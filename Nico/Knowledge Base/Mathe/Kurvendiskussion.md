---
Fach: "[[Mathe]]"
---
# Übersicht Ableitungen
## 1. Ableitung
![[Kurvendiskussion 02-07-25 14.12.23.excalidraw]]

## 2. Ableitung
![[Kurvendiskussion 02-07-25 14.16.37.excalidraw]]

# Ableiten
## Regeln
### Summenregel
$f(x) = u(x)+v(x) -> f'(x) = u'(x)+v'(x)$

### Konstantenregel
$f(x) = c*u(x) -> f'(x) = c * u'(x)$

### Produktregel
𝑓(𝑥)=𝑢(𝑥)⋅𝑣(𝑥) -> 𝑓′(𝑥)=𝑢′(𝑥)⋅𝑣(𝑥)+𝑢(𝑥)⋅𝑣′(𝑥)

### Differenzregel
$f(x) = \frac{u(x)}{v(x)} -> f'(x) = \frac{u'(x)*v(x)-u(x)*v'(x)}{v(x)^2}$

### Kettenregel
$f(x) = u(v(x)) -> f'(x) = u'(v(x))*v'(x)$

## Ableitungen

### e Funktion
$f(x) = e^u(x) -> f'(x) = e^u(x) * u'(x)$ 
**Beispiel:**
$f(x) = e^{4x^3} -> f'(x) = e^{4x^3} * 12x^2$ 

## ln Funktion
$f(x)=ln(x) ->f'(x)=\frac{1}{x}$ 

### Potenzfunktion
$f(x) = x^n -> f'(x) = n * x^{n-1}$
**Beispiel**:
$f(x) = x^3 -> f'(x) = 3x^2$ 

**Merke:**
Wenn $f(x) = x^1 = x$ dann ist $f'(x) = 1$

### Konstante Funktion
$f(x) = c -> f'(x) = 0$
**Beispiel:**
$f(x) = 2 -> f'(x) = 0$

### Wurzel
$f(x)=\sqrt{x} = x^\frac{1}{2}-> f'(x)=\frac{1}{2}x^{-\frac{1}{2}}$ 

# Diskriminante
>Mit der Diskriminante kann bestimmt werden wie viele Nullstellen die Mitternachtsformel/Funktion hat

$b^2 -4ac$ 
$>0$ : 2 Lösungen
$=0$ : 1 Lösung
$<0$ : keine Lösung

# Limes
Potenz von Zähler > Nenner -> +- Unendlich
Potenz von Nenner > Zähler -> 0
Potenzen gleich -> Faktoren betrachten

# Monotonie
1. Anhand der Hoch und Tiefpunkte Intervalle bilden
2. Testwert innerhalb des Intervall in die zweite Ableitung $f'(x)$ einsetzen
$f'(x) < 0$ : Fallend
$f'(x) > 0$ : Steigend

# Logarithmus
$log_b(a) = z <> b^z = a$  

# Extremstelle
Da wo die erste Ableitung $f'(x) = 0$ ist, ist der höchste oder tiefste Wert. 
Ob es ein Hoch oder Tiefpunkt ist kann mit der zweiten Ableitung $f''(x)$ bestimmt werden:
$f''(x) > 0$ : Tiefpunkt
$f''(x) < 0$ : Hochpunkt

# Integralrechnung
$\int_a^b f(x) dx = F(b) - F(a)$  
F ist hierbei die Stammfunktion (aufleiten)

# Krümmungsverhalten
$f''(x) > 0$ : Linkskrümmung
$f''(x) < 0$ : Rechtskrümmung
$f''(x) = 0$ : **und** $f''(x)$ hat hier VZ-Wechsel -> Wendepunkt

# Symmetrie
**Punktsymmetrisch:** $f(x) = -f(-x)$ 
Liegt vor wenn alle Exponenten ungerade sind

**Achsensymmetrisch:** $f(x) = f(-x)$
Liegt vor wenn alle Exponenten gerade sind

Liegt keins der beiden vor, hat die Funktion keine Symmetrie

# Wendepunkte
>An den Wendepunkten ändert sich die Krümmung
>!!Nicht mit Extrempunkt verwechseln!!

$f''(x) = 0$ setzen ergibt die Wendepunkte

# Winkel
Es wird der Winkel einer Gerade $f(x) = mx+t$ berechnet
$tan(\alpha) = m$ 
$f'(x) = m$
$tan^{-1}(m) = \alpha$ 
Das ist der Winkel der Gerade zur x-Achse 
(Im Taschenrechnet $tan^{-1}$ verwenden und im Display muss $d$ für Degree stehen)