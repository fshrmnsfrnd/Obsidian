---
Fach: "[[DB]]"
Thema:
  - "[[Relational Databases]]"
---
>Kardinalitäten stellen im [[ER Modell]] dar, **wie viele** [[ER Modell#Entität (Entity)|Entitäten]]  einer [[ER Modell#Entitätsmenge (Entity-Set)|Entitätsmenge]] mit  [[ER Modell#Entität (Entity)|Entitäten]]  einer anderen [[ER Modell#Entitätsmenge (Entity-Set)|Entitätsmenge]] in Verbindung stehen **können**.
# 1:1 Beziehung
---
![[Pasted image 20241109140547.png]]
**1** Student hat **1** Studentenausweis
# 1:N; N:1 Beziehung
---
![[Pasted image 20241109140659.png]]
Auf **1** Hochschule können **N** Studenten gehen
# N:M Beziehung
---
![[Pasted image 20241109140854.png]]
**1** Student geht in **N** Vorlesungen
In **1** Vorlesung gehen **1** Studenten

# Ternäre und n-äre Beziehungen
----
![[ER Modell 2024-11-09 15.00.03.excalidraw]]
(Grün) Ein Lieferant liefert für ein Produkt mehrere Bauteile. 
(Rot) Ein Bauteil, das von einem bestimmten Lieferant geliefert wird, wird in mehreren Produkten verwendet. 
(Blau) Ein bestimmtes Bauteil für ein bestimmtes Produkt wird von mehreren Lieferanten geliefert.

# Rekursive Beziehungen
---
![[ER Modell 2024-11-09 15.04.58.excalidraw]]
Ein Bauteil besteht aus einem oder mehr Bauteilen.
# Aggregation (Part-Of-Beziehung)
---
![[ER Modell 2024-11-09 15.09.32.excalidraw]]
Eine Aggregation liegt vor, wenn eine Entität aus mehreren anderen Entitäten zusammengesetzt wird.
# Generalisierung und Spezialisierung (IS-A-Beziehung)
---
![[ER Modell 2024-11-09 15.13.17.excalidraw]]
Eine IS-A Beziehung kann wie folgt überprüft werden:
- Jeder PKW ist ein Fahrzeug
- Jeder LKW ist ein Fahrzeug
- Jedes Motorrad ist ein Fahrzeug
## Unterscheidungsmerkmale von IS-A Beziehungen

| ER-Modell Name | Beschreibung                                                                    |
| -------------- | ------------------------------------------------------------------------------- |
| disjunkt       | Alle Teilmengen sind echte Teilmengen. Die Teilmengen überschneiden sich nicht. |
| nicht-disjunkt | Die Teilmengen können gemeinsame Elemente haben                                 |
| total          | Es gibt keine weiteren Teilmengen                                               |
| partiell       | Es gibt mehr Teilmengen, werden aber nicht aufgeführt                           |
