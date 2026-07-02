---
Thema:
  - "[[Redis]]"
---
>Die Strukturen sind allgemeingültig, die Commands sind [[Redis Search]] bezogen
# Strings
---
```
SET <key> <value>
GET <key> #Returns value or nil
DEL <key>
```
>Das normale "Key-Value"
```cli
127.0.0.1:6379> SET Mitarbeiter:1:Vorname "Max"  
OK   
127.0.0.1:6379> SET counter 100  
OK  
127.0.0.1:6379> GET counter  
"100"
127.0.0.1:6379> DEL counter  
(integer) 1  
127.0.0.1:6379> GET counter  
(nil)
```
# Listen
---

| Befehl                                          | Beschreibung                                                                                                          |
| ----------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `LTRIM <key> <start> <stop>`                    | Trimmt (beschneidet) eine Liste auf bestimmte Bereiche.                                                               |
| `LINSERT <key> BEFORE\|AFTER <element> <value>` | Fügt einen wert vor/nach dem Element in die Liste ein                                                                 |
| `LPOP <key> [<count>]`                          | Entfernt das erste (oder mehr mit count) Element.                                                                     |
| `BLPOP <key> <timeout>`                         | Ein Client wartet (blockiert) bis ein Element in einer Liste verfügbar ist, bevor er versucht, es zu entfernen (pop). |
| `LPUSH <key> <value>`                           | fügt Elemente am Kopf der Liste (links) ein                                                                           |
| `LRANGE <key> <start> <stop>`                   | gibt den angegebenen Teil der Liste aus                                                                               |
| `LSET <key> <index> <value>`                    | überschreibt den value am index                                                                                       |

> [!Warning] Alle Commands sind auch mit `R` statt `L` verfügbar, dann arbeiten sie vom Ende der Liste aus

```cli
127.0.0.1:6379> LPUSH meinObst "Banane"  
(integer) 1  
127.0.0.1:6379> LPUSH meinObst "Orange"  
(integer) 2  
127.0.0.1:6379> LPUSH meinObst "Apfel"  
(integer) 3
```
Rückgabewert ist die Länge der Liste
### Liste abfragen
```cli
127.0.0.1:6379> LRANGE meinObst 0 -1  
1) "Apfel"  
2) "Orange"  
3) "Banane"  
```
# Sets
---
>Sets sind wie immer unique

| Befehl                       | Beschreibung                                                                                                                                             |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `SADD <key> <member>`        | fügt Elemente in eine Menge ein                                                                                                                          |
| `SMEMBERS <key>`             | fragt alle Elemente einer Menge ab                                                                                                                       |
| `SUNION <key> [<key1>, ...]` | Gibt die Vereinigungsmenge aus mehreren Sets in einem neuen Set zurück. Soll das Ergebnis  gespeichert werden, verwenden Sie statt dessen `SUNIONSTORE`. |
| `SINTER <key> [<key1>, ...]` | Gibt die Schnittmenge aus mehreren Sets in einem neuen Set zurück. Soll das Ergebnis  <br>gespeichert werden, verwenden Sie statt dessen `SINTERSTORE`.  |
| `SDIFF <key> [<key1>, ...]`  | Gibt die Differenzmenge aus mehreren Sets in einem neuen Set zurück. Soll das Ergebnis  <br>gespeichert werden, verwenden Sie statt dessen `SDIFFSTORE`. |
```cli
127.0.0.1:6379> SADD meineFreunde "Max"  
(integer) 1  
127.0.0.1:6379> SADD meineFreunde "Moritz"  
(integer) 1  
127.0.0.1:6379> SADD meineFreunde "Willi"  
(integer) 1
127.0.0.1:6379> SADD meineFreunde "Willi"  
(integer) 1
```

```cli
127.0.0.1:6379> SMEMBERS meineFreunde  
1) "Max"  
2) "Moritz"  
3) "Willi"
```
# Hashes
---
>Ähnlich JSON

| Befehl                                                 | Beschreibung                                 |
| ------------------------------------------------------ | -------------------------------------------- |
| `HSET <key> <field> <value> [<field1> <value1>, ...]`  | fügt Elemente in eine Menge ein              |
| `HGET <key> <field>`                                   | fragt die Elemente einer Menge ab            |
| `HMSET <key> <field> <value> [<field1> <value1>, ...]` | fügt mehrere Elemente in eine Menge ein      |
| `HMGET <key> <field> [<field1>, ...]`                  |                                              |
| `HMGET <key> <field>`                                  | fragt mehrere Elemente einer Menge ab        |
| `HEXISTS <key> <field>`                                | prüft ob ein Hash existiert                  |
| `HGETALL <key>`                                        | Holt alle Felder und Werte                   |
| `RENAME <curKey> <newKey>`                             | Benennt den Hash um und behält die Attribute |
```cli
127.0.0.1:6379> HSET Person:1 nachname "Mustermann"  
(integer) 1  
127.0.0.1:6379> HSET Person:1 vorname "Max" alter 20 
(integer) 1
```

```cli
127.0.0.1:6379> HGET Person:1 nachname  
"Mustermann"
```

```cli
127.0.0.1:6379> HMSET Person:2 Nachname "Mustermann" Vorname "Moritz" Alter 25  
OK  
127.0.0.1:6379> 127.0.0.1:6379> HMGET Person:2 Nachname Vorname Alter  
1) "Mustermann"  
2) "Moritz"  
3) "25"
```
