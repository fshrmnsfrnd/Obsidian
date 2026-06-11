---
Fach: "[[DB]]"
Thema:
  - "[[Python]]"
  - "[[Schule/Databases/NoSQL/Redis/Redis|Redis]]"
---
# Session öffnen/schließen
---
## öffnen
```cli
user@system> redis-cli  
127.0.0.1:6379>
```
## beenden
```cli
127.0.0.1:6379> exit
```
# Basics
---
Für mehr Details siehe [[Schule/Databases/NoSQL/Redis/Datenstrukturen|Datenstrukturen]]

| Befehl                                      | Beschreibung                                      |
| ------------------------------------------- | ------------------------------------------------- |
| `SET <key> <value> [EX <seconds>]`          | setzt ein key value paar (evtl mit Expire time)   |
| `GET <key>`                                 | holt den wert zu einem key                        |
| `EXISTS <key>`                              | prüft ob ein key existiert                        |
| `DEL <key>`                                 | löscht einen key                                  |
| `APPEND <key> <valueToAdd>`                 | Fügt den übergebenen wert an den value an         |
| `MSET <key> <value> [<key1> <value1>, ...]` | setzt mehrere keys (Multiple SET)                 |
| `MGET <key> [<key1>, ...]`                  | holt mehrere keys (Multiple SET)                  |
| `GETSET <key> <value>`                      | Holt den aktuellen Wert und überschreibt ihn dann |
## Set
```cli
127.0.0.1:6379> SET Mitarbeiter:1:Nachname "Mustermann"  
OK
```
## Get
```cli
127.0.0.1:6379> GET Mitarbeiter:1:Nachname  
"Mustermann"
```
## Exists
```cli
127.0.0.1:6379> EXISTS Mitarbeiter:1:Nachname
(integer) 1
```
## Del
```cli
127.0.0.1:6379> DEL Mitarbeiter:1:Alter Mitarbeiter:1:Vorname
(integer) 0
```
## Key umbenennen
```cli
127.0.0.1:6379> RENAME Person:2:nnnnnachname Person:2:nachname  
OK
```
## Mehrere Keys setzen
```cli
127.0.0.1:6379> MSET Person:3:nachname "Huber" Person:3:vorname "Stefan" Person:3:alter 33  
OK
```

## Mehrere Keys lesen
```cli
127.0.0.1:6379> MGET Person:3:nachname Person:3:vorname Person:3:alter  
1) "Huber"  
2) "Stefan"  
3) "33"
```

## Increment/Decrement

| Befehl                  | Beschreibung                                    |
| ----------------------- | ----------------------------------------------- |
| `INCR <key>`            | Inkrementiert den value um 1                    |
| `DECR <key>`            | Dekrementiert den value um 1                    |
| `INCRBY <key> <toIncr>` | Inkrementiert den value um den angegebenen wert |
| `DECRBY <key> <toDecr>` | Dekrementiert den value um den angegebenen wert |

```cli
127.0.0.1:6379> INCR ort:next_id  
(integer) 1
127.0.0.1:6379> INCR ort:next_id  
(integer) 2
127.0.0.1:6379> SET ort:1:plz "90904"  
OK
```
# Index
---
## Create
`FT.CREATE <IndexName> ON hash PREFIX <numberOfPrefixes> "<Prefix>" [OPTIONS]`

| Option   | Description            |
| -------- | ---------------------- |
| TEXT     | Volltestsuche          |
| NUMERIC  | Zahlenwerte            |
| TAG      | Exakte Übereinstimmung |
| SORTABLE | Ermöglicht Sortierung  |
**Beispiel**
```cli
127.0.0.1:6379> FT.CREATE idx:movie ON hash PREFIX 1 "movie:" SCHEMA title TEXT SORTABLE release_year NUMERIC SORTABLE rating NUMERIC SORTABLE genre TAG SORTABLE 

OK
```
## Info
```cli
127.0.0.1:6379> FT.INFO idx:movie 
1) index_name 
2) idx:movie 
3) index_options 
4) (empty array) 
5) index_definition 
... 
54)<> 1) "dialect_1" 
	2) (integer) 0 
	3) "dialect_2" 
	4) (integer) 0 
	5) "dialect_3" 
	6) (integer) 0
```
## Suche mit Index
`FT.SEARCH <IndexName> "<Search>" RETURN <NumberOfAttributes> <attribut1> [attribut2 [...]]`
**Suchausdrücke**
- TEXT
	- `<text>`
	- `@<attribute>:<text>`
	- `%<text>%`
	- `<text1> | %<text2>%` (Oder)
- TAG
	- `{<TagName>}`
**Beispiel**
```bash
127.0.0.1:6379> FT.SEARCH idx:movie "war" RETURN 3 title release_year rating 
1) (integer) 1 #Anzahl Treffer
2) "movie:11002" #Key
3)  1) "title" 
   .2) "Star Wars: Episode V - The Empire Strikes Back" 
   .3) "release_year" 
   .4) "1980" 
   .5) "rating" 
   .6) "8.7"
```
# Timeouts
---
## TTL (Get Timeout)
```cli
127.0.0.1:6379> TTL <key>
(integer) 24
```
## Expire (Set Timeout)
```cli
127.0.0.1:6379> EXPIRE <key> <seconds>
(integer) 1
```
**Options:**

| Option | Beschreibung                                                    |
| ------ | --------------------------------------------------------------- |
| `NX`   | Set expiry only when the key has no expiry                      |
| `XX`   | Set expiry only when the key has an existing expiry             |
| `GT`   | Set expiry only when the new expiry is greater than current one |
| `LT`   | Set expiry only when the new expiry is less than current one ne |
## EXPIREAT (Refresh Timeout)
```cli
127.0.0.1:6379> EXPIREAT <key> <unixTimestamp>
(integer) 1
127.0.0.1:6379> EXPIRETIME <key>
(integer) 33177117420
```