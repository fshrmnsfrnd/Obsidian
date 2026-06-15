---
tags:
Fach: "[[DB]]"
Thema:
  - "[[MySQL]]"
---
```sql
SELECT [ALL|DISTINCT] 
{<ColName>[as <Alias>]|<Expression>[as <Alias>]}
[,<ColName>[as <Alias>]|<Expression>[as <Alias>], ...]
[FROM <TableName> [<Alias>], [<TableName> [<Alias>]], ...] 
[[LEFT|RIGHT|INNER] JOIN <TableName> ON <JoinCondition>] ...]
[WHERE <Condition>] 
[GROUP BY {<ColName>|<Expression>|<Position>}] 
[HAVING <Condition>] 
[ORDER BY {<ColName>|<Expression>|<Position>} 
[ASC|DESC][,...]];
```
# SELECT
---
Hier sind die die Spalten angegeben die zurückgegeben werden sollen. Das können Spalten, Aggregationen, [[Funktionen in SQL|Funktionen]] oder Berechnungen sein. Es können auch Aliase gesetzt werden(Bei Berechnungen besonders sinnvoll).
**ALL** (Default)
Gibt an, dass alle Datensätze angezeigt werden.
**DISTINCT** 
Verwirft alle doppelten Datensätze. 
# FROM
---
Hier werden die Tabellen aufgelistet, aus welchen die Spalten verwendet werden sollen. 
# WHERE
---
Hier werden die Datensätze gefiltert. Hier können Spalten und Berechnungen in Verbindung mit Vergleichs-[[Operatoren]] und Suchkriterien verwendet werden. Auch Joins können hier angegeben werden.
# [[Joins|JOIN]]
---
Hier kann eine oder mehrere zusätzliche Tabellen angegeben werden, die in die Ausgabe integriert werden sollen.
# [[Gruppierung|GROUP BY]]
---
Hier werden Spalten angegeben, aus welchen Gruppen gebildet werden. D.h. gleiche Daten in den Gruppierungs-Spalten werden zu einem Datensatz zusammengefasst. Für diese Gruppen können mittels **Aggregat-Funktionen** statistische Werte berechnet werden: z.B. `MIN(.), MAX(.), SUM(.), AVG(.), COUNT(.)`. Diese Berechnungen werden im `SELECT`-Abschnitt festgelegt.
# HAVING
---
Das WHERE des GROUP BY.
Hier werden die berechneten Werte aus dem `GROUP BY` Abschnitt gefiltert. Es ist nicht möglich, die berechneten Werte im `WHERE`-Abschnitt zu filtern, da die Berechnung erst nach der Filterung stattfindet.
# ORDER BY
---
Hier wird die Reihenfolge angegeben in der die Daten angezeigt werden sollen. Es kann auch nach mehreren Spalten gruppiert werden.
**ASC** 
(engl. ascending) 
ASC gibt an, dass die Werte dieser Spalte aufsteigend sortiert werden – also von kleinen hin zu großen Werten. ASC ist der Standardwert, wenn er hinter einer Spalte bzw. Einer Berechnung fehlt. 
**DESC** 
(engl. descending) 
DESC gibt an, dass die Werte dieser Spalte absteigend sortiert werden – also von großen hin zu kleinen Werten.