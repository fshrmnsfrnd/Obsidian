---
Fach: "[[DB]]"
tags:
Thema:
  - "[[MySQL]]"
---
# Erstellen
---
## Datenbank
```sql
CREATE DATABASE [IF NOT EXISTS] dbname;
```

## Tabelle
```sql
CREATE TABLE [IF NOT EXISTS] Table1 ( 
	id INT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY ,
	txt VARCHAR(100) NOT NULL, 
	zahl INT NOT NULL, 
	zahl2 INT UNSIGNED NOT NULL, 
	CONSTRAINT FK_Adresse_Ort FOREIGN KEY (zahl2) REFERENCES Table2 (zahl2)
)
```
### Erklärung:
Tabelle erstellen
PRIMARY KEY wird automatisch vergeben (AUTO_INKREMENT) ist eine positive Ganzzahl
Text bis 100 Zeichen darf nicht leer sein
Ganzzahl
Positive Ganzzahl
Foreign key der in Tabelle 2 referenziert
# Anzeigen
---
## Datenbanken anzeigen
```sql
SHOW DATABASES;
```
## Tabellen anzeigen
```sql
SHOW TABLES [FROM dbName] [LIKE ‘muster’];
```
# Auswählen
---
```sql
USE dbname;
```
# Ändern
---
```sql
ALTER TABLE tabellen_name_alt RENAME TO tabellen_name_neu;
ALTER TABLE tabellen_name DROP COLUMN colName;
ALTER TABLE tabellen_name ADD COLUMN colName Datentyp;
ALTER TABLE tabellen_name MODIFY COLUMN colName andererDatentyp;
ALTER TABLE tabellen_name CHANGE COLUMN colName newColName VARCHAR(40);
```
# Löschen
---
> [!WARNING] 
> Gelöschte Strukturen und ihre Inhalte können nicht wiederhergestellt werden.
## Datenbank löschen
```sql
DROP DATABASE [IF EXISTS] dbname;
```
## Tabelle löschen
```sql
DROP TABLE [IF EXISTS] tabellen_name;
```

> [!NOTE] 
> Wenn die Tabelle einen Primary Key hat, der in anderen Tabellen als Foreign Key verwendet wird kann die Tabelle nicht gelöscht werden. Wenn es einen View gibt, der auf die Tabelle zugreift, kann sie ebenfalls nicht gelöscht werden

