---
Fach: "[[DB]]"
tags:
Thema:
  - "[[MySQL]]"
---
# Definieren
---
```sql
DELIMITER ||
CREATE PROCEDURE <ProcedureName>()
BEGIN
	<Statement>;
END ||
DELIMITER ;
```
Der Delimiter wird geändert, damit das Statement nicht mittendrin beim erstellen der Prozedur aufhört, sondern es nur so speichert.
# Parameter
---
```sql
DELIMITER ||
CREATE PROCEDURE <ProcedureName>([[IN | OUT | INOUT] <parameter_name> <data_type>])
BEGIN
	<Statement>;
END
DELIMITER ;
```
### Modi der Parameter

| Mode  | Erklärung                                                                                                                                                                                                                                                                                                                                |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IN    | Ist der default. Bedeutet, dass der Wert vom aufrufenden Programm angegeben werden muss und Änderungen, die am Parameter im gespeicherten Programm vorgenommen werden, nicht über das aufrufende Programm abgerufen werden können.                                                                                                       |
| OUT   | Ein OUT-Parameter kann vom gespeicherten Programm geändert werden, und der geänderte Wert kann aus dem aufrufenden Programm abgerufen werden. Das aufrufende Programm muss eine Variable bereitstellen, um die Ausgabe des OUT- Parameters zu empfangen. Out-Parameter haben zunächst den Wert NULL.                                     |
| INOUT | Ein INOUT-Parameter fungiert sowohl als IN- als auch als OUT-Parameter. Das heißt, das aufrufende Programm kann einen Wert bereitstellen, das gespeicherte Programm selbst kann den Wert des Parameters ändern, und das aufrufende Programm kann auf diesen geänderten Wert zugreifen, wenn das gespeicherte Programm abgeschlossen ist. |
#### Beispiel IN
```sql
DELIMITER || 
CREATE PROCEDURE studenten_herkunft (IN nation_nr INT) 
BEGIN 
	SELECT * FROM studenten WHERE nation = nation_nr; 
END|| 
DELIMITER ;
```

#### Beispiel OUT
```sql
DELIMITER || 
CREATE PROCEDURE anzahl (OUT n INT) 
BEGIN 
	SELECT COUNT(BNr) INTO n FROM studenten; 
END|| 
DELIMITER ;

CALL anzahl(@x);
SELECT @x;
```
# Aufrufen
---
```sql
CALL <procedureName>();
```
# Löschen
---
```sql
DROP PROCEDURE [IF EXISTS] <ProcedureName>;
```
