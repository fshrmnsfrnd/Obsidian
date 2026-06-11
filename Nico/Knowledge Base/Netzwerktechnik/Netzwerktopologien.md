---
Fach:
tags:
Thema:
  - "[[Networks]]"
---
# Bus
---
Alle Stationen teilen sich das gemeinsame **Übertragungsmedium** (**Shared Medium**)
![[Pasted image 20251030142134.png]]

| **Vorteile**               | **Nachteile**                                         |
| -------------------------- | ----------------------------------------------------- |
| Einfacher Aufbau           | Störanfällig                                          |
| nur eine Leitung Notwendig | langsam                                               |
|                            | Eine defekte Station kann das gesamte netz lahm legen |
# Stern
---
![[Pasted image 20251030142140.png]]

|**Vorteile**|**Nachteile**|
|---|---|
|Störsicher|hoher Verkabelungsaufwand|
|Wenn eine Station ausfällt ist nicht das ganze Netz betroffen|Single-Point-of-Failure|
# Mesh
---

|**Vorteile**|**Nachteile**|
|---|---|
|hohe Ausfallsicherheit|erfordert Viele Verbindungen|
|schnell|teuer|
||schwierig zu Verwalten|
## Vollständig
**Jede** Station ist mit **Jeder** anderen Station verbunden.  
![[Pasted image 20251030142201.png]]
Anzahl der Verbindungsleitungen bei $n$ Stationen:  
L=∑i=1n−1iL=∑i=1n−1​i  
im Beispiel n=5n=5: L=1+2+3+4=10L=1+2+3+4=10

$$
L = \sum_{i=1}^{n-1} i
$$
im Beispiel:
$n=5; L=1+2+3+4=10$ 
## Unvollständig
Nicht jede Station ist mit Jeder Verbunden. Wird z. B.: bei LAN, WAN, Internet verwendet.  
Je mehr Querverbindungen es gibt, desto Ausfallsicherer ist das Netz.
![[Pasted image 20251030142225.png]]
# Ring
---
![[Pasted image 20251030142151.png]]

|**Vorteile**|**Nachteile**|
|---|---|
|Einfacher Aufbau|sehr Störanfällig|
|Nur eine Leitung notwendig|langsam|
# Cell
---
Topologie für drahtlose Netze
![[Pasted image 20251030142246.png]]

|**Vorteile**|**Nachteile**|
|---|---|
|keine Kabel nötig|langsam|
||anfällig für Störungen|
