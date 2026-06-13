---
tags:
Fach: "[[DB]]"
Thema:
  - "[[MySQL]]"
---
# User anlegen
---
```sql
CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';
```
# Rechte anzeigen
---
```sql
SHOW GRANTS [FOR user@host]
```
# Rechte vergeben
---
```sql
GRANT Zugriffsrechte 
ON [Datenbank.]Tabelle[.Spalte] 
TO user@host [WITH GRANT OPTION]
```
WITH GRANT OPTION beschreibt ob der User seine Rechte weitergeben darf, oder nicht.
## Privilegien / Zugriffsrechte
| PRIVILEG                 | Beschreibung                                                                                                                                                           |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ALL`                    | Alle Rechte, außer dem `GRANT`-Recht, werden vergeben.                                                                                                                 |
| `ALTER`                  | Tabellenstruktur darf verändert werden.                                                                                                                                |
| `CREATE`                 | Tabellen dürfen angelegt werden.                                                                                                                                       |
| `CREATE TEMPORARY TABLE` | Temporäre Tabellen dürfen angelegt werden.                                                                                                                             |
| `DELETE`                 | Datensätze dürfen gelöscht werden.                                                                                                                                     |
| `DROP`                   | Tabellen dürfen entfernt werden.                                                                                                                                       |
| `EXECUTE`                | [[Stored Procedures]] dürfen ausgeführt werden.                                                                                                                        |
| `FILE`                   | Dateien des lokalen Dateisystems dürfen gelesen und verändert werden (z. B. für Datenimport und -export).                                                              |
| `INDEX`                  | Index darf angelegt und entfernt werden.                                                                                                                               |
| `INSERT`                 | Datensätze dürfen eingefügt werden.                                                                                                                                    |
| `LOCK TABLES`            | Tabellen dürfen blockiert werden.                                                                                                                                      |
| `PROCESS`                | MySQL-Prozesse anderer Benutzer dürfen aufgelistet werden.                                                                                                             |
| `RELOAD`                 | Verschiedene Kommandos (z. B. `FLUSH PRIVILEGES`) dürfen ausgeführt werden.                                                                                            |
| `REPLICATION CLIENT`     | Informationen über die Teilnehmer eines Replikationssystems dürfen eingeholt werden.                                                                                   |
| `REPLICATION SLAVE`      | Ermöglicht das Lesen der Master-BinLogs.                                                                                                                               |
| `SELECT`                 | `SELECT`-Anweisungen dürfen ausgeführt werden.                                                                                                                         |
| `SHOW DATABASES`         | Die Namen der installierten Datenbanken können ausgegeben werden.                                                                                                      |
| `SHUTDOWN`               | Der MySQL-Server darf heruntergefahren werden.                                                                                                                         |
| `SUPER`                  | MySQL-Prozesse anderer Benutzer können beendet werden. [[Stored Procedures]] und Trigger dürfen erzeugt und geändert werden. Admin-Kommandos dürfen ausgeführt werden. |
| `UPDATE`                 | Das Ändern von Datensätzen ist möglich.                                                                                                                                |
| `USAGE`                  | Alle Privilegien eines Users können gesperrt werden (quasi keine Rechte).                                                                                              |
# Rechte entziehen
---
```sql
REVOKE Zugriffsrechte 
ON [Datenbank.]Tabelle[.Spalte] 
FROM user@host;
```
# Verwaltung
---
>Die Verwaltung der Zugriffsrechte erfolgt in der Datenbank mysql. 
## User
```sql
SHOW Columns FROM mysql.user;
```

| Host      | User  | authentication_string | SELECT_priv | DELETE_priv | ..._priv |
| --------- | ----- | --------------------- | ----------- | ----------- | -------- |
| localhost | User1 | `$A$005$HashedPwd`    | Y           | N           | Y/N      |
## Andere Tabellen

| Tabelle             | Beschreibung                                                                               |
| ------------------- | ------------------------------------------------------------------------------------------ |
| `mysql.db`          | Welcher User hat welche Rechte in welcher Datenbank (Globale Rechte werden nicht beachtet) |
| `mysql.tables_priv` | Haben auf eine Tabelle nicht alle User Zugriff werden die Berechtigungen hier gespeichert  |
| `mysql.colums_priv` | Haben auf eine Spalte nicht alle User Zugriff werden die Berechtigungen hier gespeichert   |
|                     |                                                                                            |
