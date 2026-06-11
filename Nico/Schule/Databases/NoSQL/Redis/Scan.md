---
Fach: "[[DB]]"
Thema:
  - "[[Schule/Databases/NoSQL/Redis/Redis|Redis]]"
---
Der Befehl `SCAN` benötigt einen anfänglichen Cursor-Wert, der typischerweise 0 ist. Er gibt einen neuen  
Cursor-Wert für die nächste Iteration und eine Liste der in der aktuellen Iteration gefundenen Schlüssel zurück.

```cli
127.0.0.1:6379> SCAN 0  
1) "11"  
2) 1) "Person.1"  
3) "Person:3:alter"  
4) "Person:2:nachname"  
5) "meinObst"  
6) "Mieter:3"  
7) "Mitarbeiter:1:Nachname"  
8) "Person:3:nachname"  
9) "Mieter:6"  
10) "Mieter:4"  
11) "Mieter:1"  
12) "Mitarbeiter:1:Vorname"
```
"11": Wir sind noch nicht fertig. Es wird ein zweiter Scan benötigt, der mit 11 beginnt
```cli
127.0.0.1:6379> SCAN 11  
13) "0"  
14) 1) "Person:3:vorname"  
15) "Mieter:5"  
16) "Mieter:2"  
17) "meineFreunde"
```
"0": Wir sind fertig. Es wird kein weiter Scan benötigt.
# SCAN mit Filter
---
```cli
127.0.0.1:6379> SCAN 0 Match Mieter* 
1) "11" 
2) 1) "Mieter:3" 
	.2) "Mieter:6" 
	.3) "Mieter:4" 
	.4) "Mieter:1" 
   
127.0.0.1:6379> SCAN 11 Match Mieter* 1) "0" 2) 1) "Mieter:5" 2) "Mieter:2"
```