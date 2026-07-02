---
Thema:
  - "[[MySQL]]"
---
# IF
---
```sql
IF Bedingung THEN
	Anweisungen 
[ELSEIF Bedingung THEN
	Anweisungen] 
[ELSE
	Anweisungen] 
END IF;
```
# CASE
---
```sql
CASE Ausdruck
	WHEN value_1 THEN 
		Anweisungen
	[WHEN value_n THEN 
		Anweisungen] 
	[ELSE
		Anweisungen]
END CASE;
```

> [!WARNING] Eine CASE-Anweisung löst eine Exception aus, wenn keine der Bedingungen zutrifft! 
> Der Fehlercode lautet: `MySQL error 1339`. 
> Deshalb immer ein `ELSE` verwenden
