---
tags:
Fach: "[[DB]]"
Thema:
  - "[[MySQL]]"
---
# Erstellen
```sql
CREATE Trigger <triggerName>
<triggerTime> <triggerEvent> ON <tabelName>
FOR EACH {ROW|STATEMENT} <triggerStatement>; 
```

`<triggerTime>: BEFORE | AFTER`
- ``BEFORE``: der Trigger wird ausgeführt, bevor eine Zeile eingefügt/geändert/gelöscht wird.
- `AFTER`: der Trigger wird ausgeführt, nachdem eine Zeile eingefügt/ geändert/gelöscht wurde.

`<triggerEvent>: INSERT|UPDATE|DELETE`
- `INSERT`: der Trigger wird ausgeführt, wenn neue Zeilen eingefügt werden.
- `UPDATE`: der Trigger wird ausgeführt, wenn Spalten geändert werden. 
- `DELETE`: der Trigger wird ausgeführt, wenn Datensätze gelöscht werden
# Löschen
---
```sql
DROP TRIGGER <triggerName>;
```
# Beispiel
---
```sql
delimiter || 
CREATE TRIGGER nachlass 
	BEFORE UPDATE ON kunden FOR EACH ROW 
	BEGIN 
		IF NEW.Kaufsumme<=100 THEN SET NEW.Rabatt=0; 
		ELSEIF NEW.Kaufsumme>100 AND NEW.Kaufsumme<=500 THEN SET NEW.Rabatt=1;
		ELSE SET NEW.Rabatt=2; 
		END IF; 
	END; ||
```