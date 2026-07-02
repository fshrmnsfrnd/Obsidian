---
Thema:
  - "[[MySQL]]"
---
Mit einem Cursor kann man nacheinander durch die einzelnen Datensätze einer Abfrage gehen. Cursor gibt es in [[Stored Procedures]], und [[Trigger]]

Die Cursor in MySQL haben folgende Eigenschaften: 
- **schreibgeschützt**: Ein Cursor ist nur zum lesen der Daten da
- **nicht scrollbar**: Man kann nur gerade durch alle Datensätze rotieren. Es gibt kein zurück oder überspringen o.ä.
- **asensitiv**: MySQL-Cursor arbeiten auf den tatsächlichen Daten oder auf einer Kopie. Die Entscheidung liegt beim Datenbankserver. Unter diesem Aspekt kann ein Cursor in MySQL entweder sensitive oder insensitive sein. 

**Sensitive Cursor:** Greift ähnlich eines Pointers live auf die Daten zu, sie werden nicht zwischengespeichert, sondern direkt aus der Datenbank gelesen.
**Insensitive Cursor:** Der Cursor ist schreibgeschützt und es wird eine temporäre Kopie der Daten erstellt. 
**Asensitive Cursor:** Ein asensitiver Cursor lässt der Datenbank die Entscheidung, ob der Cursor sensitive oder insensitive implementiert wird. Meistens wird er wie insensitive behandelt; es sei denn, die Engine kann sensitiv arbeiten.
# Übersicht
---
```sql
# DECLARE <variableForFetch> [Datatype];

DECLARE finished BOOLEAN DEFAULT FALSE; 
DECLARE <cursor_name> CURSOR FOR <select_statement>;
DECLARE CONTINUE HANDLER FOR NOT FOUND SET finished = TRUE;

OPEN <cursor_name>;
	loop_cursor:REPEAT
	FETCH <cursor_name> INTO <variableForFetch>[ ,...];
		# Code
	UNTIL finished END REPEAT loop_cursor;
CLOSE <cursor_name>;
```
# Deklarieren
---
```sql
DECLARE <cursor_name> CURSOR FOR <select_statement>;
```
# Öffnen
---
```sql
OPEN <cursor_name>;
```
# Verwenden
---
```sql
FETCH <cursor_name> INTO <variable1>[ ,...];
```
Hier muss die Anzahl und Reihenfolge der [[Variablen in SQL|Variablen in SQL]] zum Select Statement aus der Deklaration passen. 
Die Variablen müssen vorher deklariert sein.
# Ende des Cursors erkennen
---
```sql
DECLARE finished BOOLEAN DEFAULT FALSE; 
... 
DECLARE CONTINUE HANDLER FOR NOT FOUND SET finished = TRUE;
```
# Schließen
---
```sql
CLOSE <cursor_name>;
```