---
Fach: "[[DB]]"
tags:
Thema:
  - "[[MySQL]]"
---
>Änderungen die innerhalb einer Transaktion gemacht wurden, werden erst in die Datenbank geschrieben, sobald die gesamte Transaktion fehlerfrei durchgelaufen ist
# Auto Commit
---
```sql
SET AUTOCOMMIT = 0;
```
Hiermit werden Transaktionen der einzelnen Befehle ausgeschalten, und sie können zu einer großen Transaktion zusammengefasst werden.

# Eigene Transaktionen
---
### Beginn der Transaktion:
`START TRANSACTION;`

### Schreiben der Transaktion in die Datenbank:
`COMMIT;`
oder ein beliebiger Befehl aus der [[Kategorien der SQL Befehle#DDL (Data Definition Language)|DLL]] .

### Verwerfen der Änderungen
`ROLLBACK;`
Verwirft alles was seit Beginn der Transaktion gemacht wurde.

# ACID
---
## Atomicity
Es werden entweder alle Befehle der Transaktion ausgeführt oder keiner.
## Consistency
Die Datenbank muss nach der Transaktion in einem konsistenten Zustand sein. Sonst muss `ROLLBACK` ausgeführt werden.
## Isolation
Es müssen mehrere Transaktionen gleichzeitig laufen können, ohne dass sie sich beeinflussen oder stören. (Auch durch Queue lösbar)
## Durability
Die Transaktion muss auch bei einem Hardware Serverabsturz noch korrekt ausgeführt werden.

# Mögliche Fehler bei parallelen Transaktionen
---
## Lost Update
Die Transaktionen greifen hier leicht versetzt auf die selben Daten zu.

| Transaktion 1     | Transaktion 2     |
| ----------------- | ----------------- |
| Ändern Daten 1    |                   |
|                   | Ändern Daten 1    |
| Schreiben Daten 1 |                   |
|                   | Schreiben Daten 1 |
Hier wird das Schreiben der Daten 1 aus Transaktion 1 durch Transaktion 2 wieder überschrieben. Somit wurde Transaktion 1 zwar Fehlerfrei ausgeführt, aber die Änderungen sind trotzdem nicht in der Datenbank.

## Dirty Read
Eine Transaktion liest die Daten, die von einer anderen Transaktion danach wieder zurückgerollt werden.

| Transaktion 1     | Transaktion 2     |
| ----------------- | ----------------- |
| Lesen Daten 1     |                   |
| Schreiben Daten 1 |                   |
|                   | Lesen Daten 1     |
|                   | Schreiben Daten 1 |
| ROLLBACK          |                   |
|                   | COMMIT            |
Transaktion 2 arbeitet mit den Daten von Transaktion 1, welche aber falsch sind, da Transaktion 1 abgebrochen wird.

## Phantom

| Transaktion 1 | Transaktion 2     |
| ------------- | ----------------- |
| Lesen Daten 1 |                   |
|               | Schreiben Daten 1 |
| Lesen Daten 1 |                   |
Für Transaktion 1 haben sich aus unersichtlichen Gründen die Daten geändert.