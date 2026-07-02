---
Thema:
  - "[[MySQL]]"
---
- Es gibt nur IN Parameter, diese müssen nicht mit IN gekennzeichnet werden
- Die Funktion selbst muss einen einzelnen Wert zurückgeben, dessen Typ im Header der Funktion definiert ist. 
- Funktionen können in SQL-Anweisungen aufgerufen werden. 
- Eine Funktion gibt möglicherweise keine Ergebnismenge zurück
# Unterschied Stored Procedure <-> Stored Function
---

|                                      | Stored Function                 | Stored Procedure                                 |
| ------------------------------------ | ------------------------------- | ------------------------------------------------ |
| Rückgabewert                         | Genau **einen** Wert (`RETURN`) | Keinen, einen oder mehrere (via `OUT`-Parameter) |
| Aufruf                               | `SELECT myFunction()`           | `CALL myProcedure()`                             |
| OUT / INOUT Parameter                | Nein                            | Ja                                               |
| Transaktionen (`COMMIT`, `ROLLBACK`) | Nein                            | Ja                                               |
| Fehlerbehandlung (`SIGNAL`, Handler) | Eingeschränkt                   | Voll unterstützt                                 |
| Mehrere Resultsets zurückgeben       | Nein                            | Ja (mehrere SELECTs)                             |
| Charakteristiken im Header           | Pflicht                         | Optional                                         |

# Definition
---
```sql
DELIMITER || 
CREATE FUNCTION <FunctionName> (<variable> <Datatype>[, ...]) 
[RETURNS <Datentyp>]
[NOT] DETERMINISTIC 
[CONTAINS SQL | NO SQL | READS SQL DATA | MODIFIES SQL DATA]
[SQL SECURITY DEFINER | INVOKER]
[COMMENT 'Text']
BEGIN
	#Code 
	[RETURN <Value>; ]
END || 
DELIMITER ;
```
## Charakteristiken
### Deterministic
Gibt an, ob die Funktion bei **gleichen Eingabewerten immer dasselbe Ergebnis** liefert.

| Keyword             | Bedeutung                                                                |
| ------------------- | ------------------------------------------------------------------------ |
| `DETERMINISTIC`     | Gleiche Parameter → immer gleiches Ergebnis                              |
| `NOT DETERMINISTIC` | Ergebnis kann variieren (z. B. wegen `NOW()`, `RAND()`, Tabellenzugriff) |
### Datenzugriffs Charakteristik
#### `NO SQL`
Die Funktion enthält **keinerlei SQL-Statements** – nur reine Logik (Berechnungen, String-Operationen etc.).
```sql
CREATE FUNCTION addiere(a INT, b INT) 
RETURNS INT
NO SQL DETERMINISTIC
RETURN a + b;
```
#### `CONTAINS SQL` 
>(Standard, wenn nichts angegeben)_

Die Funktion enthält SQL, aber **liest oder schreibt keine Daten** 
```sql
SET @var = 1
```
#### `READS SQL DATA`
Die Funktion **liest Daten** aus Tabellen (`SELECT`), verändert aber nichts.
```sql
CREATE FUNCTION get_name(id INT) RETURNS VARCHAR(100)
READS SQL DATA NOT DETERMINISTIC
BEGIN
  DECLARE result VARCHAR(100);
  SELECT name INTO result FROM kunden WHERE kunden_id = id;
  RETURN result;
END;
```
#### `MODIFIES SQL DATA`
Die Funktion **schreibt in Tabellen** (`INSERT`, `UPDATE`, `DELETE`).
> Achtung: In Stored Functions ist das erlaubt, aber mit Einschränkungen – z. B. nicht überall aufrufbar (nicht in `SELECT` direkt).
### SQL SECURITY
Legt fest, **mit wessen Rechten** die Funktion ausgeführt wird:

| Keyword                | Bedeutung                                             |
| ---------------------- | ----------------------------------------------------- |
| `DEFINER` _(Standard)_ | Läuft mit den Rechten des **Erstellers** der Funktion |
| `INVOKER`              | Läuft mit den Rechten des **aufrufenden Users**       |
# Aufruf
---
```sql
SELECT <FunctionName>([paramValue])
```
# Löschen
---
```sql
DROP FUNCTION [IF EXISTS] <FunctionName>;
```