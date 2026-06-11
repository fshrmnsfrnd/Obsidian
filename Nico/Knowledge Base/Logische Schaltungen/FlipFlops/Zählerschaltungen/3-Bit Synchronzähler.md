---
Fach:
tags:
Thema:
  - "[[Logische Schaltungen]]"
---
# Ermittlung der Anwendungsgleichung eines 3-Bit Synchronzählers

| $t^m$ |       |       |     | $t^{m+1}$ |       |       |     | Dezimalziffern |
| ----- | ----- | ----- | --- | --------- | ----- | ----- | --- | -------------- |
| $q_c$ | $q_b$ | $q_a$ |     | $q_c$     | $q_b$ | $q_a$ |     |                |
| 1     | 1     | 1     |     | 0         | 0     | 0     |     | 0              |
| 0     | 0     | 0     |     | 0         | 0     | 1     |     | 1              |
| 0     | 0     | 1     |     | 0         | 1     | 0     |     | 2              |
| 0     | 1     | 0     |     | 0         | 1     | 1     |     | 3              |
| 0     | 1     | 1     |     | 1         | 0     | 0     |     | 4              |
| 1     | 0     | 0     |     | 1         | 0     | 1     |     | 5              |
| 1     | 0     | 1     |     | 1         | 1     | 0     |     | 6              |
| 1     | 1     | 0     |     | 1         | 1     | 1     |     | 7              |
| 1     | 1     | 1     |     | 0         | 0     | 0     |     | 0              |
$q_a^{m+1} = [(\bar{q_a} \land \bar{q_b} \land \bar{q_c}) \lor (\bar{q_a} \land q_b \land \bar{q_c}) \lor (\bar{q_a} \land \bar{q_b} \land q_c) \lor (\bar{q_a} \land q_b \land q_c)]^m$  

## Vereinfachung im KV-Diagramm

> [!WARNING] Achtung
> Keine Vereinfachung über die aktuelle Variable! (Hier: $q_a , \bar{q_a}$ müssen erhalten bleiben)

### 1. Anwendungsgleichung $q_a$
![[D-FlipFlop 03-06-25 09.01.33.excalidraw]]

$q_b^{m+1} = [(q_a \land \bar{q_b} \land \bar{q_c}) \lor (\bar{q_a} \land q_b \land \bar{q_c}) \lor (q_a \land \bar{q_b} \land q_c) \lor (\bar{q_a} \land q_b \land q_c)]^m$ 
### 2. Anwendungsgleichung $q_b$
![[D-FlipFlop 03-06-25 09.18.46.excalidraw]]
### 3. Anwendungsgleichung $q_c$
![[D-FlipFlop 03-06-25 09.25.37.excalidraw]]
# 1.
$q_a^{m+1} = \bar{q_m}^m$ (Anwendungsgleichung 1. D-FF)
$q_a^{m+1} = d_a$ (Charakteristische Gleichung D-FF)
V Koeffizientenvergleich V
$d_a = \bar{q_a}$

![[D-FlipFlop 03-06-25 09.33.39.excalidraw]]

# 2. 
$q_b^{m+1} = (q_a \land \bar{q_b}) \lor (\bar{q_a} \land q_b)$ Anwendungsgleichung 2. D-FF
$q_b^{m+1} = d_b$
V Koeffizientenvergleich V
$d_b = (q_a \land \bar{q_b}) \lor (\bar{q_a} \land q_b)$

