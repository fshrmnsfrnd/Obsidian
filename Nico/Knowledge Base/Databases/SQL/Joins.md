---
Thema:
  - "[[MySQL]]"
---

![[Pasted image 20250515091506.png]]
# Kartesischer Join (Cross Join)
---
>Der CROSS JOIN verknüpft jede Zeile aus der ersten Tabelle mit allen Zeilen aus der zweiten Tabelle:

```sql
SELECT m.nachname, m.vorname, s.sportart 
FROM mitglied m CROSS JOIN sportart s; 
SELECT m.nachname, m.vorname, s.sportart
FROM mitglied m, sportart s;
```

Wozu sollte man den CROSS JOIN kennen? 
- Sensibilisierung für den Fall fehlender Verknüpfungen 
- einfaches Erzeugen von Massendaten für Geschwindigkeitstests
# Inner Join
---
>Ein INNER JOIN kombiniert die Datensätze zweier Tabellen über Vergleichsoperatoren in einer Bedingung.
## Equi Join

Variante 1: 
```sql
SELECT m.nachname, m.vorname, l.sport_id 
FROM mitglied m 
INNER JOIN link_mitglied_sportart l ON m.m_id = l.m_id;
```
Variante 2: 
```sql
SELECT m.nachname, m.vorname, l.sport_id 
FROM mitglied m, link_mitglied_sportart l WHERE m.m_id = l.m_id;
```
### Equi Join mit mehreren Tabellen
Variante 1: 
```sql
SELECT m.nachname, m.vorname, s.sportart 
FROM mitglied m 
INNER JOIN link_mitglied_sportart l ON m.m_id = l.m_id 
INNER JOIN sportart s ON l.sport_id = s.sport_id;
```
Variante 2: 
```sql
SELECT m.nachname, m.vorname, s.sportart 
FROM mitglied m, link_mitglied_sportart l, sportart s 
WHERE m.m_id = l.m_id AND l.sport_id = s.sport_id;
```
# Natural Join
---
>NATURAL JOINs werden durch identische Spaltennamen identifiziert. D.h. es werden alle Spalten verknüpft, die in den abgefragten Tabellen gleich heißen. Diese Art des Joins kann zu Fehlern führen, wenn nachträglich Spaltennamen in den beteiligten Tabellen geändert werden.

```sql
SELECT m.nachname, m.vorname, l.sport_id 
FROM mitglied m NATURAL JOIN link_mitglied_sportart l
```
# Outer Join
---
## Left Outer Join
>Der LEFT OUTER JOIN selektiert alle Datensätze aus der linken Tabelle und die Zeilen aus der rechten Tabelle, die der Verknüpfung entsprechen.

… A LEFT OUTER JOIN B ... 
- Zeige alle Datensätze aus A und die aus B, die gleich sind. 
- Fehlende DS in B werden als NULL Spalten dargestellt. 
- Filter sind anwendbar.

```sql
SELECT m.m_id, m.nachname, m.vorname, l.sport_id 
FROM mitglied m 
LEFT OUTER JOIN link_mitglied_sportart l ON m.m_id = l.m_id;
```
## Right Outer Join
… A RIGHT OUTER JOIN B ... 
- Zeige alle Datensätze aus B und die aus A, die gleich sind. 
- Fehlende DS in A werden als NULL Spalten dargestellt. 
- Filter sind anwendbar.

```sql
SELECT l.m_id, l.sport_id, s.sport_id, s.sportart FROM link_mitglied_sportart l RIGHT OUTER JOIN sportart s ON l.sport_id = s.sport_id;
```
## Full Outer Join
>Manche DBS ermöglichen auch einen FULL OUTER JOIN als eine Kombination aus LEFT OUTER JOIN und RIGHT OUTER JOIN MySQL nicht!
## Fehlende Datensätze Filtern
>Fehlende Datensätze werden im Ergebnis der Abfrage als NULL-Werte angezeigt. Diese NULL-Werte können im WHERE-Abschnitt gefiltert werden: 

`WHERE spalte IS NULL`
# Self Join
---
>Es ist ebenfalls möglich, eine Tabelle mit sich selbst zu verknüpfen. Man spricht hier von einem SELF-JOIN. Der Tabellennamen wird in der FROM-Klausel zweimal angegeben. Es müssen dafür zwei unterschiedliche Alias Namen vergeben werden.

```sql
SELECT vg.m_id, vg.vorname, vg.nachname, ma.m_id, ma.vorname, ma.nachname 
FROM mitarbeiter vg 
INNER JOIN mitarbeiter ma ON vg.m_id = ma.chef_id
```
