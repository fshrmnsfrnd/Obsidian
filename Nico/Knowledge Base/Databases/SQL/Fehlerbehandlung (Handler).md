---
Thema:
  - "[[MySQL]]"
---
>Handler können nur in [[Stored Functions]] oder [[Stored Procedures]] verwendet werden
# Definition
---
```sql
DECLARE {CONTINUE | EXIT}-HANDLER FOR 
{SQLSTATE sqlstate_code | MySQL-Fehlercode | condition_name | SQLWARNING | NOT FOUND | SQLEXCEPTION} handler_actions
```
Die Definition muss **nach** der Deklaration aller Variablen, und **vor** allen ausführbaren Anweisungen stattfinden.
# Handler Bedingungen
---
- einen MySQL-Fehlercode verwenden
- einen ANSI-Standard SQLSTATE-Code verwenden
- eine benannte Bedingung definieren
- `SQLWARNING` (Abkürzung für die SQLSTATE-Fehlerklasse '01')
- `NOT FOUND` (Abkürzung für die SQLSTATE-Fehlerklasse '02'),
- `SQLEXCEPTION` (Abkürzung für die nicht zu den SQLSTATE-Fehlerklassen '01' und '02' gehören)
# Handler-Typen
---
## Continue
>Bei einem **CONTINUE HANDLER** wird die Ausführung mit der Anweisung fortgesetzt, die auf die verursachende Anweisung folgt.
### Beispiel
```sql
DELIMITER ||
CREATE PROCEDURE myProcedure ()
BEGIN
	DECLARE err INT DEFAULT 0;
	DECLARE CONTINUE HANDLER FOR <MYSQL_ERROR_NR> SET err=1;
	
	# Statements
	IF(err=1)THEN
		SELECT "Ein Fehler ist aufgetreten!" as "Result";
	ELSE
		SELECT <Ergebnis> as "Result";  
	END IF; 
END||
DELIMITER ;

CALL myProcedure;
```
## EXIT
>Wenn ein **EXIT HANDLER** ausgelöst wird, wird der aktuell ausgeführte Block beendet. Wenn dieser Block der Hauptblock für das gespeicherte Programm ist, wird die Prozedur beendet, und die Steuerung an den Aufrufenden Codeblock zurückgegeben
### Beispiel
```sql
DELIMITER ||
CREATE PROCEDURE add_department(in_dept_name VARCHAR(30), 
								in_location VARCHAR(30), 
								in_manager_id INT) 
MODIFIES SQL DATA
BEGIN 
	DECLARE duplicate_key INT DEFAULT 0;
	BEGIN
		DECLARE EXIT HANDLER FOR 1062 SET duplicate_key=1;
		INSERT INTO departments (department_name,location,manager_id)
			VALUES(in_dept_name,in_location,in_manager_id); 
		SELECT CONCAT('Department ',in_dept_name,' created') as "Result"; 
	END;
	IF duplicate_key=1 THEN 
		SELECT CONCAT('Failed to insert ',in_dept_name, 17 ': duplicate key') 
		as "Result"; 
	END IF; 
END||
DELIMITER ;
```
