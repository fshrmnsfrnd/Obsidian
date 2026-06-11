---
tags:
Fach: "[[DB]]"
Thema:
  - "[[MySQL]]"
---
# Having
---
```sql
SELECT column_name(s)  
FROM table_name  
WHERE condition  
GROUP BY column_name(s)  
HAVING condition  
ORDER BY column_name(s);
```
>Having ist sozusagen die `WHERE` Bedingung von `GROUP BY`,

Beispiel: Wenn pro Gruppe (`GROUP BY`) eine Anzahl (`SUM`) bestimmt werden soll, und nach der Anzahl gefiltert werden soll, geht das nur mit `HAVING`, weil `WHERE` filtert **bevor** die Aggregation stattgefunden hat. Mit `WHERE` könnte man z.B. filtern welche Datensätze überhaupt gezählt werden sollen.
# Summe pro Attribut
---
```sql
SELECT vorname,SUM(verkaeufe) 
FROM kuchenverkaeufe 
GROUP BY vorname 
ORDER BY SUM(verkaeufe) DESC;
```
# Durchschnitt pro Attribut
---
```sql
SELECT vorname,AVG(verkaeufe) 
FROM kuchenverkaeufe 
GROUP BY vorname;
```
# Min und Max
---
```sql
SELECT vorname,MIN(verkaeufe) 
FROM kuchenverkaeufe 
GROUP BY vorname;
```

```sql
SELECT vorname,MAX(verkaeufe) 
FROM kuchenverkaeufe 
GROUP BY vorname;
```
# Anzahl Mitglieder pro Gruppe (n<->m)
---
```sql
SELECT s.Sportart, COUNT(lms.M_Id)
FROM sportart s
LEFT JOIN link_mitglied_sportart lms ON s.Sport_Id = lms.Sport_ID
GROUP BY s.Sportart;
```