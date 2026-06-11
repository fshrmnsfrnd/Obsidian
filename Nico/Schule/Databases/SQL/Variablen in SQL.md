---
Fach: "[[DB]]"
tags:
Thema:
  - "[[MySQL]]"
---
# Deklarieren
---
```sql
DECLARE <Name> <Datentyp> [DEFAULT <Initialisierungswert>];
SET <Name> = <Wert>;
```
## Beispiele
---
```sql
DELIMITER || 
CREATE PROCEDURE sp_demo_variables() 
BEGIN 
	DECLARE v_int INT DEFAULT -10; 
	DECLARE v_int_positiv INT UNSIGNED default 300; 
	DECLARE v_bigint1 BIGINT DEFAULT 4000000000000000; 
	
	DECLARE v_float FLOAT DEFAULT 1.5e8; 
	DECLARE v_double DOUBLE DEFAULT 2e40; 
	DECLARE v_numeric NUMERIC(10,2) DEFAULT 21.35; 
	
	DECLARE v_date DATE DEFAULT '2021-09-14'; 
	DECLARE v_datetime DATETIME DEFAULT '2021-09-14 23:59:59'; 
	
	DECLARE v_char CHAR(255) DEFAULT 'immer 255 Zeichen'; 
	DECLARE v_varchar VARCHAR(255) DEFAULT 'variabler Text'; 
	DECLARE v_text TEXT DEFAULT 'Ein sehr langer Text'; 
END|| 
DELIMITER ;
```
# Werte setzen und ändern
---
```sql
DELIMITER || 
CREATE PROCEDURE sp_demo_variables_assignment() 
	BEGIN DECLARE i,j,k INTEGER; SET i = 10; -- Werte auf 10 setzen 
	SELECT i,j,k; -- Ausgabe: 10,NULL,NULL 
	SET i = 1, j = 2, k = 3; -- Werte ändern 
	SELECT i,j,k; -- Ausgabe: 1,2,3 
END|| 
DELIMITER ;
```

# Datentypen
---
![[Datentypen in SQL]]
# Benutzervariablen
---
Sind im Prinzip Globale Variabeln
```sql
SELECT 'Ich bin eine Benutzer-Variable:' into @message;
SELECT @message;
SET @message = 5;
```
Auf Benutzervariablen kann von überall zugegriffen werden.