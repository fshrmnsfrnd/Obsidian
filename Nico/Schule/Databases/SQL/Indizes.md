---
Fach: "[[DB]]"
Thema:
  - "[[MySQL]]"
---
>Ein Index ist eine Datenstruktur, die auf einer oder mehreren Spalten einer Tabelle erstellt wird, um den schnellen Zugriff auf Datensätze zu ermöglichen. 

# Funktionsweise
---
Indizes erstellen eine geordnete Repräsentation der Daten, wodurch Suchvorgänge optimiert werden. 
In folgenden Fällen sollten Indizes verwendet werden: 
- Bei häufigen Suchvorgängen. 
- Bei Abfragen mit JOIN-Operationen. 
- Bei Bedarf nach eindeutigen Werten in einer Spalte. 
### Drauf sollte geachtet werden: 
- Nicht übermäßig viele Indizes erstellen, um unnötigen Speicherverbrauch zu vermeiden. 
- Indizes regelmäßig überprüfen und gegebenenfalls neu erstellen, um die Leistung beizubehalten. 
- Indizes beschleunigen die Abfragen, können aber dazu führen, dass sich das Einfügen, Ändern und Löschen verlangsamt; Grund dafür ist die Reorganisation der Index-Datei. 
- Indizes funktionieren am besten bei Spalten, deren Werte stark variieren und deren Datenmenge klein ist: kurze Texte, Datums-Felder, etc. Eine Spalte mit Ja- oder Nein-Werten ist weniger geeignet. 
- Wird eine Spalte indiziert, die NULL-Werte enthält, werden nur die Datensätze in den Index aufgenommen, die Werte in der Index-Spalte haben
# Indizes erzeugen
---
## `Create Index`
```sql
CREATE INDEX index_name ON table_name(col1);
CREATE UNIQUE INDEX index_name ON table_name(col1);

# Mehrspaltenindex
CREATE INDEX index_name ON table_name(col1, col3);
CREATE UNIQUE INDEX index_name ON table_name(col2, col4);
```

## `Create Table`
```sql
CREATE TABLE table_name (
	col1 VARCHAR(250), 
	..., 
	INDEX(col1)
);

# Mehrspaltenindex
CREATE TABLE table_name (
	col1 VARCHAR(250), 
	col2 INT,
	..., 
	INDEX(col1, col2)
);
```

## `Alter Table`
```sql
ALTER TABLE table_name ADD INDEX(col);

# Mehrspaltenindex
ALTER TABLE table_name ADD INDEX(col1, col2);
```

# Arten von Indizes
---
### Clustered Index
- Speichert die Daten sortiert **physikalisch** ab
- Eine Tabelle kann nur **einen** haben
- Bei MySQL wird der Primärschlüssel automatisch als Clustered Index angelegt.
### Non-Clustered Index
- Hier wird nur eine Liste von **Referenzen** zu den Daten gespeichert
- Eine Tabelle kann mehrere haben
### Composite Index
- Ein Index der sich auf **mehrere** Spalten bezieht
### Partial Index
- Nur ein **Teil** des Datensatzes wird indiziert
### Unique Index
- Werte darin sind **eindeutig**
- Wird standardmäßig mit dem Primary Key erstellt
- Es kann mehrere pro Tabelle geben
# Indizes auf Keys
---
### Primärindex
Bei vielen DBMS wird der Primary Key als Clustered Index realisiert.
### Foreign Key als Index
Foreign-Key-Spalten können, müssen aber nicht mit einem Index ausgestattet werden. Ob ein Index sinnvoll ist, hängt davon ab, welche Art von Abfragen Sie häufig ausführen. In MySQL werden für Foreign-Key-Spalten automatisch Indizes angelegt. Bei anderen DBMS ist das nicht so.
# Pages
---
Die meisten DBMS organisieren den verwalteten Datenspeicher in Blöcken, die als Pages bezeichnet werden. Die Blockgröße variiert je nach DBMS; 4 kB, 8 kB und 16 kB sind die gebräuchlichsten Werte.

Nach Möglichkeit versucht das DBMS, jeden Datensatz vollständig in einer Page zu speichern. Reicht der verbleibende Platz für den nächsten Datensatz nicht mehr aus, landet dieser in einer neuen Page; der restliche Speicherplatz der vorigen Page bleibt (vorerst) ungenutzt.

Die Pages befinden sich in einer gewöhnlichen Datei. Am gängigsten ist es, pro Datenbank eine große Datei vorzusehen, die sowohl Daten als auch Indizes aufnimmt.

Längere Texte (TEXT) oder größere binäre Objekte (BLOB) werden aus Performance-Gründen getrennt vom restlichen Datensatz gespeichert.

Abhängig vom DBMS gibt es unterschiedliche Konzepte: 
- Daten und Indizes werden in getrennten Dateien gespeichert. 
- Jede Tabelle und eventuell jeder Index wird in einer eigenen Datei gespeichert. 
- Alle Datenbanken inklusive aller Tabellen und Indizes werden in einer gemeinsamen, riesigen Datei gespeichert.
## Fragmentierung 
Durch das Löschen des Datensatzes entsteht dort, wo sich die Daten ursprünglich befanden, ungenutzter freier Speicherplatz. 
Je mehr derartige *Löcher* es in den Pages gibt, desto **stärker** gilt der Speicher als fragmentiert. Bei Datenbanken, in denen vorhandene Daten häufig geändert werden, muss das DBMS nach Wegen suchen, den ungenutzten Speicherplatz wieder verwendbar zu machen. Diesen Vorgang nennt man *Reorganisation* oder *Defragmentierung*. Dabei werden Seiten mit einem hohen Anteil ungenutzter Bytes komplett in eine neue Seite übertragen; die alte Seite wird als Speicherplatz für andere Daten freigegeben. Abhängig von DBMS muss diese Reorganisation angestoßen werden, oder sie läuft selbständig im Hintergrund.
# Nice to Know
---
- Eine Tabelle kann nur einen *Primärindex* haben
- Eine Tabelle kann mehrere Indizes haben
- `null` Werte werden nicht indiziert
- Ein Index über mehrere Spalten beschleunigt nur Abfragen wenn die Spalten in Reihenfolge verwendet werden(Von hinten her darf weggelassen werden)
	- `INDEX(A, B)` beschleunigt **nur** 
		- `... WHERE a = <value> AND b = <value>`
		- `... WHERE a = <value>`
		- `... ORDER BY a, b ...`
- Indizes machen zwar lesen schneller, schreiben dafür langsamer (Beim [[Indizes#Clustered Index|Clustered Index]] beides extrem)
- `BLOB`s sollten nicht indiziert werden
- `Index` $\ne$ `Query Cache` Der Query Cache speichert Ergebnisse von Queries
- Indizes speichern die Daten als [[B Trees|B Tree]] 