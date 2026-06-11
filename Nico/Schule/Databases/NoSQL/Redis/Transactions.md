---
Fach: "[[DB]]"
Thema:
  - "[[Schule/Databases/NoSQL/Redis/Redis|Redis]]"
---

> [!WARNING]  In Python werden dafür Pipelines verwendet
# Starten
```cli
127.0.0.1:6379> MULTI  
OK
127.0.0.1:6379(TX)> SET Inventar:2:titel "HP-Drucker"  
QUEUED  
127.0.0.1:6379(TX)> SET Inventar:2:raum "BP 1.01"  
QUEUED
```
# Änderungen ausführen
```cli
127.0.0.1:6379(TX)> EXEC  
1) OK  
2) OK
```
# Änderungen verwerfen
```cli
127.0.0.1:6379(TX)> DISCARD  
OK
```
