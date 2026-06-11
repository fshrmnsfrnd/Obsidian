---
tags:
Fach: "[[DB]]"
Thema:
  - "[[MySQL]]"
---
# Daten einfügen
---
```sql
INSERT INTO tableName(col1, col2, col3)
VALUES (1, 'a', 1.5)
```

> [!NOTE] Die Spaltennamen können auch weggelassen werden, dann muss aber exakt auf die Reihenfolge geachtet werden, in der die Spalten erstellt wurden (Nicht zu empfehlen)
# Daten ändern
---
```sql
UPDATE tableName
SET colName1 = newValue1,
	colName2 = newValue2
WHERE colName3 = value
```

> [!WARNING] Wird keine Filterung verwendet, werden alle Datensätze geändert
# Daten löschen
---
```sql
DELETE 
FROM tableName
WHERE colName = value
```

> [!WARNING] Wird keine Filterung verwendet, werden alle Datensätze gelöscht. Es können keine Spalten, nur Datensätze gelöscht werden



