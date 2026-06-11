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
- Kein eigenes **Ende**, nur ein Semikolon am Ende der gesamten Abfrage
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
Eine Unterabfrage ist eine **nicht-korrelierte** Unterabfrage, wenn sie eigenständig ist und nichts aus der äußeren Abfrage verwendet oder referenziert. Bei einer nicht-korrelierten Unterabfrage wertet das DBMS zuerst die innere Abfrage bzw. die Unterabfrage aus, bevor die äußere Abfrage ausgeführt wird.
### Beispiel
```sql
SELECT name, gehalt
FROM mitarbeiter
WHERE gehalt > (
    SELECT AVG(gehalt)
    FROM mitarbeiter
);
```
- Die **Unterabfrage** `(SELECT AVG(gehalt) FROM mitarbeiter)` wird **einmal** ausgeführt.
- Das Ergebnis (der Durchschnitt) wird dann mit jedem einzelnen Gehalt verglichen.
- Die Unterabfrage ist **nicht abhängig** von der äußeren Abfrage.
## Korrelierte Unterabfrage
Eine Unterabfrage kann auch **korreliert** sein. In diesem Fall ist die Unterabfrage abhängig von Werten, die die äußere Abfrage liefert. In diesem Fall ist die Ausführung der inneren Abfrage von den Daten der äußeren Abfrage abhängig. Ist eine Unterabfrage korreliert, wertet das DBMS zunächst die äußere Abfrage aus. Für jeden Datensatz der äußeren Abfrage wird die Unterabfrage ausgeführt und die Daten ermittelt. Man spricht in diesem Fall von einer **nested-loop-Semantik**. Zwar ist eine beliebige Schachtelung möglich, jedoch besteht die Gefahr, das die Ausführung von solchen Abfragen sehr lange dauert.
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
- Die **Unterabfrage** hängt von der **aktuellen Zeile** der äußeren Abfrage ab (`m2.abteilung = m1.abteilung`).
- Sie wird für **jede Zeile** der äußeren Abfrage **neu ausgeführt**.
- Das macht die Abfrage korreliert: Die Unterabfrage **korreliert** mit der äußeren Abfrage.