---
Fach: "[[Programmieren]]"
Thema:
  - "[[UML]]"
---
Ein Zustandsdiagramm besteht aus:
- einer endlichen Menge von Zuständen
- einer endlichen Menge von Ereignissen
- Transitionen, die den Übergang von einem Zustand in den nächsten beschreiben
- einem Anfangszustand
- einem Endzustand oder mehreren Endzuständen
![[Pasted image 20260305084831.png]]
# Zustände (States)
---
Ein Zustand ist eine Kombination von möglichen Attributwerten, die Objekte einer Klasse haben können. 
Ein Zustand hat folgende Merkmale:
- Ein Zustand hat einen eindeutigen **Namen**
- Zwei Zustände mit dem **selben** **Namen** sind **identisch**
- Ein Zustand **ohne Namen** ist ein **anonymer** Zustand
- **Anonyme** Zustände sind grundsätzlich voneinander **verschieden**
- Jeder Zustand wird durch die **Werte** einer oder auch mehrerer Zustandsvariablen **definiert**
- Ein Objekt kann von einem in einen anderen zustand wechseln. Diese **Zustandsübergänge** werden durch Ereignisse ausgelöst
- Ein **Ereignis** wird durch einen **Namen** und einer **Liste** von erlaubter Argumenten dargestellt.
## Notation
### Basic Zustand
![[Pasted image 20260324230855.png]]
### Zustand mit Aktion bei Ereignis
![[Pasted image 20260324230932.png]]
### Zustand mit Aktion bei Ereignis mit Guard(Bedignung)
![[Pasted image 20260324231034.png]]
### Arten von Aktionen in Zuständen
![[Pasted image 20260324231121.png]]
### Anonymer Zustand
![[Pasted image 20260324231150.png]]
# Ereignisse (Transitions)
---
Folgende Merkmale beschreiben eine Transition: 
- **Zustandsübergänge** werden durch Transitions ausgelöst.
- Transitions werden als **Pfeile** zwischen zwei Zuständen dargestellt.
- Die **Transitionsbeschriftung** wird auf den Pfeil geschrieben.
- Transitions können mit **Bedingungen** versehen werden.
## Notation
![[Pasted image 20260324231414.png]]
## Arten von Transitions
### CallEvent
![[Pasted image 20260324231557.png]]
### SignalEvent
![[Pasted image 20260324231639.png]]
### ChangeEvent
![[Pasted image 20260324231651.png]]
### TimeEvent
![[Pasted image 20260324231702.png]]
# Besondere Zustände
---
Das sind Steuerungselemente, keine echten Zustände.
Die wichtigsten sind:
- Startzustand
- Terminator
- Endzustand
- Austrittspunkt 
	- Kreis mit X darin am Übergang zwischen Transition und Zustand
	- Bedeutet was genau?
- Eintrittspunkt
	- Ein leerer Kreis am Übergang von Transition zu Zustand
	- Bedeutet was genau?
![[Pasted image 20260324231929.png]]
# Kreuzung (Fork)
---
- Eine Kreuzung prüft seine Entscheidung **im** von der Kreuzung aufgerufenen Zustand.
- Die Abfolge ist im Zustandsdiagramm **statisch** festgelegt.
- Es werden **immer alle** Pfade ausgeführt
![[Pasted image 20260324232836.png]]
Im Beispiel wird in Arbeit gewechselt

**Vorteil:**
![[Pasted image 20260324234536.png]]
# Entscheidung (Decision)
---
- Eine Entscheidung prüft seine Entscheidung **nach** dem Zustand.
- Entscheidet während der Laufzeit des Programmes in welchen Zustand gewechselt wird. 
- Nur Pfade deren Guard `true` ist werden ausgeführt
![[Pasted image 20260324232910.png]]
Im Beispiel wird in Entspannung gewechselt