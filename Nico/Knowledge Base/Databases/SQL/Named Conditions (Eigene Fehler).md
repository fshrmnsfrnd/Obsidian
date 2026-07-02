---
Thema:
  - "[[MySQL]]"
---
```sql
DECLARE <condition_name> CONDITION FOR {SQLSTATE sqlstate_code | MySQL_error_code} [Handler Actions];
```
oder lesbarer:
```sql
DECLARE <condition_name> CONDITION FOR{SQLSTATE sqlstate_code | MySQL_error_code};
DECLARE CONTINUE HANDLER FOR <condition_name> {Action on Error};
```
# Eigene Fehlermeldungen erzeugen
---
```sql
DECLARE <own_error> CONDITION FOR SQLSTATE SQLSTATE '45000';]

SIGNAL {<own_error>|SQLSTATE '45000'} SET MESSAGE_TEXT=<'Own Error Message'>, MYSQL_ERRNO = {>=50000};
```
Syntax:
```sql
SIGNAL condition_value  
	[SET signal_information_item [, signal_information_item] ...]

condition_value:  
	{ SQLSTATE [VALUE] sqlstate_value | condition_name }  

signal_information_item:  
	condition_information_item_name = simple_value_specification  

condition_information_item_name:  
	{ CLASS_ORIGIN  
	| SUBCLASS_ORIGIN  
	| MESSAGE_TEXT  
	| MYSQL_ERRNO  
	| CONSTRAINT_CATALOG  
	| CONSTRAINT_SCHEMA  
	| CONSTRAINT_NAME  
	| CATALOG_NAME  
	| SCHEMA_NAME  
	| TABLE_NAME  
	| COLUMN_NAME  
	| CURSOR_NAME }
```

> [!NOTE] 
> Eigene Fehlernummer sind frei wählbar im Bereich zwischen: 50000-51999
## Beispiel
```sql
DECLARE own_error CONDITION FOR SQLSTATE '45000';
IF error = 1 THEN
	SIGNAL own_error SET MESSAGE_TEXT='fehler geworfen', MYSQL_ERRNO = 50001;
END IF;
```
