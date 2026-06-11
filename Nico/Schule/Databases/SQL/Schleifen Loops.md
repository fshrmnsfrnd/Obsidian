---
Fach: "[[DB]]"
Thema:
  - "[[MySQL]]"
---
# Übersicht
---
```sql
myLabel:LOOP
	-- Ich bin ein Endless Loop
END LOOP myLabel;
```
# LEAVE
---
```sql
SET i = 1; 
myloop:LOOP 
	SET i = i + 1; 
	IF i = 5 THEN
		LEAVE myloop;
	END IF;
END LOOP myloop;
```
# ITERATE
---
```sql
DECLARE i INT;
SET i = 0;
ungerade_zahlen: LOOP
	SET i = i + 1;

	/*Hier wird die Schleife beendet*/
	IF i >= 10 THEN
	LEAVE ungerade_zahlen;

	/* gerade Zahlen überspringen*/
	ELSEIF i % 2 = 0 THEN
		ITERATE ungerade_zahlen;
	END IF;
	SELECT CONCAT(i," ist ungerade");
END LOOP ungerade_zahlen;
```
- Springt wenn `ITERATE` erreicht wird wieder zum Anfang der Schleife
# REPEAT UNTIL
---
```sql
SET i = 0; 
ungerade_zahlen:REPEAT 
	SET i = i + 1; 
	IF i % 2 <> 0 THEN 
		Select concat(i," ist ungerade."); 
	END IF; 
UNTIL i >= 5 
END REPEAT ungerade_zahlen;
```
# WHILE
---
```sql
DECLARE i INT;
SET i = 1; 
loop1:WHILE i <= 5 DO 
	IF MOD(i,2) <> 0 THEN 
		SELECT CONCAT(i," ist ungerade."); 
	END IF; 
	SET i = i + 1; 
END WHILE loop1;
```