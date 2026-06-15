---
tags:
Fach: "[[DB]]"
Thema:
  - "[[MySQL]]"
---
# Regeln
---
- Ist immer ein **SELECT**-Statement
- Immer in **runden** Klammern
- Kein eigenes **Ende**, nur **ein** Semikolon am Ende der gesamten Abfrage
- Können mit INSERT-, DELETE-, UPDATE- und SELECT-Statements verwendet werden
- Können an **vier** Stellen in einer SELECT-Anweisung verwendet werden:
	- SELECT
	- WHERE
	- GROUP BY
	- HAVING
# Korrelation
---
>Korrelation beschreibt, ob die Unterabfrage abhängig von der äußeren Abfrage ist.
## Nicht korrelierte Unterabfrage
- Unabhängig von der äußeren Abfrage
- Innere Abfrage wird vom DBMS zuerst ausgeführt
- Wird ein einziges Mal ausgeführt
**Beispiel**
```sql
SELECT name, gehalt
FROM mitarbeiter
WHERE gehalt > (
    SELECT AVG(gehalt)
    FROM mitarbeiter
);
```
## Korrelierte Unterabfrage
- Unterabfrage hängt vom aktuellen Datensatz der äußeren Abfrage ab
- Innere Abfrage wird für jede Zeile der äußeren Abfrage neu ausgeführt
- Dauert möglicherweise sehr lange
### Beispiel
```sql
SELECT name, gehalt, abteilung
FROM mitarbeiter m1
WHERE gehalt > (
    SELECT AVG(gehalt)
    FROM mitarbeiter m2
    WHERE m2.abteilung = m1.abteilung
);
```
# Snippets
---
Eklige Aufgabe Einnahmen pro Sportart und Gesamteinnahmen
```sql
SELECT
    so.Sportart,
    (
        SELECT COUNT(lmsi.Sport_ID) * so.Beitrag
        FROM link_mitglied_sportart lmsi
        WHERE lmsi.Sport_ID = so.Sport_Id
    ) AS Einnahmen,
    (
        (
        SELECT COUNT(lmsi.Sport_ID) * so.Beitrag
        FROM link_mitglied_sportart lmsi
        WHERE lmsi.Sport_ID = so.Sport_Id
    ) * 100 / (
        SELECT Sum(sub2_s.Beitrag)
		FROM sportart sub2_s
        INNER JOIN link_mitglied_sportart sub2_l ON sub2_s.Sport_ID = sub2_l.Sport_ID
    )
    )AS AnteilAnGesamt,
    (
        SELECT Sum(sub2_s.Beitrag)
		FROM sportart sub2_s
        INNER JOIN link_mitglied_sportart sub2_l ON sub2_s.Sport_ID = sub2_l.Sport_ID
    ) as Gesamt
FROM sportart so;
```