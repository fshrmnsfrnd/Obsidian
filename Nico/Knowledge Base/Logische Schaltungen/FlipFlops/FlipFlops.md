---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---

# Schaltzeichen
![[Pasted image 20250508120304.png]]

# Zustände des Flipflops

**Setzen**: $e_1 = 1$ führt zu $q = 1$ 
Besteht bereits der Zustand $q=1$ am Ausgang, so bewirkt $e_1=1$ keine Änderung des Ausgangszustands.  

**Rücksetzen:** $e_2 = 1$ führt zu $\bar{q} = 1$ bzw. $q=0$  
$e_1 = 0 \lor e_2 = 0$ => keine steuernde Wirkung.  
Gleichzeitiges setzen on $e_1=e_2 = 1$ ist i. d. R. in Abhängigkeit der Flipflop-Art verboten.  
Der Zustand $q$ stellt den Speicherstand des Flipflops dar.  
 
**Beispiel:** $q=1$ -> Flipflop speichert den Wert $1$

## Aufbau eines Flipflops mit NOR-Gliedern

![[Pasted image 20250508121957.png]]

| $e_2$ | $e_1$ | $q_1$ | $q_2$ |              |
| ----- | ----- | ----- | ----- | ------------ |
| 0     | 0     | X     | X     | Speicherfall |
| 0     | 1     | 0     | 1     | Setzen       |
| 1     | 0     | 1     | 0     | Rücksetzen   |
| 1     | 1     | 0     | 0     | Verboten     |
$e_1 e_2 q_2^m q_1^m


| $e_1$ | $e_2$ | $q_2^m$     | $q_1^m$     |
| ----- | ----- | ----------- | ----------- |
| 0     | 0     | $q_2^{m-1}$ | $q_1^{m-1}$ |
| 0     | 1     | 0           | 1           |
| 1     | 0     | 1           | 0           |
| 1     | 1     | 0           | 0           |
$q^{m}$ : aktueller Ausgangszustand
$q^{m-1}$ : vorhergehender Ausgangszustand

## Aufbau eines Flipflops mit NAND-Gliedern
![[Pasted image 20250508130201.png]]

|e2​|e1e1​|q2q2​|q1q1​| |
|---|---|---|---|---|
|0|0|0|0|verbotener Zustand|
|0|1|1|0|Rücksetzten|
|1|0|0|1|Setzen|
|1|1|q2m−1q2m−1​|q1m−1q1m−1​|Speicherzustand|

![[Pasted image 20250508130249.png]]

| e2​ | e1e1​ | q2mq2m​     | q1mq1m​     |                    |
| --- | ----- | ----------- | ----------- | ------------------ |
| 0   | 0     | q2m−1q2m−1​ | q1m−1q1m−1​ | Speicherzustand    |
| 0   | 1     | 0           | 1           | Setzen             |
| 1   | 0     | 1           | 0           | Rücksetzen         |
| 1   | 1     | 0           | 0           | verbotener Zustand |
![[Schaltwerke 08-05-25 13.03.15.excalidraw]]

# Statische und dynamische Eingänge
## statische Eingänge
Ansprache auf den Zustand am Eingang

## dynamische Eingänge
Ansprache auf Zustandsänderung am Eingang

![[Schaltwerke 08-05-25 13.06.31.excalidraw]]

# Darstellung von verknüpften Eingängen eines Flipflops

![[Flipflops 13-05-25 08.38.48.excalidraw]]

## Abhängigkeitsnotation
![[Flipflops 13-05-25 08.57.45.excalidraw]]
### Auszug aus der Buchstabenkennzeichnung
C => Steuerung
G => UND
N => Negation
R => Rücksetzen
S => Setzen
V => ODER

# Taktflankensteuerung
- Mit der Taktflankensteuerung können die FF synchron geschaltet werden, wodurch die Störfälligkeit einer Schaltung verringert wird. (Siehe Zeitablauf Diagramm der Taktflankensteuerung)
- TF-Steuerung wird durch Impulsglieder realisiert
