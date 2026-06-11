---
tags:
Fach: "[[DB]]"
Thema:
  - "[[MySQL]]"
---
# Übersicht
```sql
SELECT [ALL|DISTINCT] 
{col_name[as alias]|expression[as alias] 
[,col_name[as alias]|expression [as alias]]} 
[FROM table_references] 
[WHERE where_condition] 
[GROUP BY {col_name|expression|position}] 
[HAVING where_condition] 
[ORDER BY {col_name|expression|position} 
[ASC|DESC][,...]];
```

## Der SELECT - Abschnitt 
Dieser Abschnitt enthält entweder eine Spalte aus einer Tabelle zur reinen Anzeige oder einen Ausdruck, der Berechnungen mit [[Operatoren]] und [[Funktionen in SQL|Funktionen in SQL]] enthalten kann. Bei Berechnungen werden häufig mathematische [[Operatoren]] verwendet. 

## ALL 
Das Schlüsselwort ALL gibt an, dass alle Datensätze angezeigt werden. Wird es weggelassen, werden standardmäßig alle Datensätze angezeigt.

## DISTINCT 
Verwirft alle Datensätze , die in der Ergebnismenge doppelt sind. 

## Der FROM – Abschnitt 
In diesem Abschnitt wird die Tabelle oder werden die Tabellen aufgelistet, die die Spalten und damit auch die Daten enthalten, die ausgewertet werden sollen. Zusätzlich wird angegeben, wie das DBMS die Daten aus den verwendeten Tabellen verknüpfen soll. Das bedeutet, vorhandene PK- und FK-Beziehungen werden nicht automatisch verwendet. Darüber hinaus besteht die Möglichkeit, Daten auf jede gewünschte Weise zu verknüpfen – wenn das nötig und sinnvoll ist. 
## Der WHERE – Abschnitt 
In diesem Abschnitt werden die Datensätze gefiltert. Das geschieht durch die Angabe von Suchkriterien. Hier können Spalten und Berechnungen in Verbindung mit Vergleichs-[[Operatoren]] und Suchkriterien verwendet werden. 
## Der GROUP BY – Abschnitt 
In diesem Abschnitt werden Spalten angegeben, um aus Datensätzen Gruppen zu bilden. D.h. gleiche Datenkombinationen in den Gruppierungs-Spalten werden zu einem Datensatz zusammengefasst. Für diese Gruppen können mittels Aggregat-Funktionen statistische Werte berechnet werden: z.B. `MIN(.), MAX(.), SUM(.), AVG(.), COUNT(.)`. Diese Berechnungen werden im `SELECT`-Abschnitt festgelegt.
## Der HAVING – Abschnitt 
Dieser Abschnitt dient dazu, berechnete Aggregate nach erfolgter [[Gruppierung]] und Berechnung über Kriterien zu filtern. D. h. in diesem Abschnitt werden Aggregat-Funktionen mit Vergleichs-[[Operatoren]] und Suchkriterien verwendet. Siehe: SQL, DQL, Gruppierung von Daten. Wichtig: Es ist nicht möglich, berechnete Aggregate im WHERE-Abschnitt zu filtern!
## Der ORDER BY – Abschnitt 
In diesem Abschnitt wird angegeben, wie die Datensätze im Ergebnis sortiert werden sollen. Dazu werden die Spalten und berechnete Ausdrücke angegeben, die für die Sortierung berücksichtigt werden sollen. Hinter jeder Spalte oder jedem Ausdruck wird die Sortierreihenfolge angegeben. 
## ASC (engl. ascending) 
ASC gibt an, dass die Werte dieser Spalte aufsteigend sortiert werden – also von kleinen hin zu großen Werten. ASC ist der Standardwert, wenn er hinter einer Spalte bzw. Einer Berechnung fehlt. 
## DESC (engl. descending) 
DESC gibt an, dass die Werte dieser Spalte absteigend sortiert werden – also von großen hin zu kleinen Werten.