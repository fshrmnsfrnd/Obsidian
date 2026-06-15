---
Fach: "[[DB]]"
Thema:
  - "[[Databases]]"
  - "[[Java]]"
---
**Object Relational Mapping**

>Java-Objekte sollen persistent in relationalen Datenbanken gespeichert werden, ohne dass Entwickler manuelles SQL schreiben müssen.

# Kernkonzepte
---
- Entity
	- Java-Klasse, die eine Datenbanktabelle repräsentiert. 
- Attribute
	- Felder der Klasse entsprechen den Spalten der Tabelle. 
- Session / EntityManager
	- Schnittstelle zur Verwaltung von Datenbankoperationen. 
- Lazy Loading
	- Objektdaten werden nur bei Bedarf geladen, spart Speicher und reduziert unnötige Abfragen. 
- Eager Loading
	- Daten werden sofort geladen, wenn die Entität abgefragt wird. 
- Caching
	- Speichert häufig genutzte Daten im Speicher, um wiederholte Datenbankzugriffe zu vermeiden. 
- Identity Management
	- Verwaltung eindeutiger IDs und Identität von Entitäten, um Datenintegrität zu gewährleisten.

# +/-
---
## **Vorteile**
- Weniger manuelles SQL. 
- Konsistentes Mapping zwischen Objekten und Datenbank. 
- Einfachere Wartung, Erweiterung und Refactoring.
## **Nachteile**
- Lernkurve bei komplexen Mappings. 
- Performance-Probleme bei falscher Nutzung. 
- Overhead bei sehr großen Datenmengen.

# Mapping Strategien
---
### Table-per-Class
- Jede Klasse hat ihre eigene Tabelle. 
- *Vorteil*: klare Struktur. 
- *Nachteil*: komplexe [[Joins]] bei Vererbung. 
### Single Table
- Alle Klassen einer Hierarchie in einer Tabelle. 
- *Vorteil*: schnelle Abfragen. 
- *Nachteil*: viele NULL-Werte. 
### Joined Table
- Jede Klasse hat eigene Tabelle, Vererbung via [[Joins]]. 
- *Vorteil*: gute [[Normalisierung]]. 
- *Nachteil*: komplexere Queries. 
### Embeddables
- Wiederverwendbare eingebettete Objekte. 
- *Vorteil*: sauberes Domain-Modell. 
- *Nachteil*: mehr Mapping-Aufwand.

# [[Transact Control Language TCL|Transaktionen]]
---
### ACID
Ausführlich: [[Transact Control Language TCL#ACID]]
- Atomicity
- Consistency
- Isolation
- Durability. 
### Optimistic Locking
- Jede Entität erhält eine Versionsnummer oder einen Zeitstempel. 
- Bei einem Update prüft das ORM, ob die Versionsnummer noch aktuell ist. 
- Wenn ein anderer Benutzer die Entität bereits geändert hat, schlägt das Update fehl (OptimisticLockException). 
- *Vorteil*: Keine dauerhaften Sperren, gute Performance bei wenig Konflikten. 
- *Nachteil*: Konflikte müssen manuell behandelt werden. 
### Pessimistic Locking: 
- Sperrt Datensätze während einer Transaktion, sodass andere Benutzer nicht gleichzeitig Änderungen vornehmen können. 
- Typische Anwendung bei hochfrequenten gleichzeitigen Zugriffen oder kritischen Operationen.
- *Vorteile*: Verhindert konkurrierende Änderungen, Datenintegrität wird gewahrt. 
- *Nachteile*: Kann zu Blockierungen und Performanceproblemen führen, Deadlocks möglich

# Querys
---
### HQL / JPQL: 
- Objektbasierte Abfragesprachen, arbeiten auf Entitäten und deren Attributen, nicht auf Tabellen und Spalten. 
- Unterstützen [[Joins]], Aggregationen, Subqueries und Gruppierungen. 
- *Vorteil*: Plattformunabhängig, objektorientiert, leicht in Java-ORM-Projekte integrierbar. 
- *Nachteil*: Weniger performant bei extrem komplexen Abfragen im Vergleich zu nativen SQLQueries.
### Criteria API: 
- Typsichere programmatische Erstellung von Queries. 
- Unterstützt komplexe Bedingungen, [[Joins]], Gruppierungen und Aggregationen. 
- Besonders nützlich bei dynamischen Suchfunktionen, bei denen Abfragen zur Laufzeit zusammengesetzt werden. 
- *Vorteil*: Fehler durch falsche Strings werden vermieden, dynamische Queries leicht zu erstellen. 
- *Nachteil*: Etwas umfangreicher im Code als einfache HQL/JPQL-Queries. 
### Native SQL Queries: 
- Direkte SQL-Abfragen bei komplexen Anforderungen. 
- Direkte SQL-Abfragen auf die Datenbank, bypassing ORM-Abstraktion. 
- *Vorteil*: Volle Kontrolle über die SQL-Syntax und Datenbank-spezifische Features. Geeignet für sehr komplexe oder performancekritische Abfragen, die mit HQL/JPQL schwierig zu realisieren sind. 
- *Nachteil*: Weniger portabel, da SQL-Dialekte der jeweiligen Datenbank berücksichtigt werden müssen. 
- Einsatzbeispiel: komplexe [[Joins]], Bulk-Updates, [[Stored Procedures]] oder Datenbank-Funktionen.

# Caching Ebenen
---
### First-Level Cache: 
- Scope: Session/EntityManager. 
- Automatisch aktiv, speichert Entitäten während einer Session. 
- *Vorteil*: Vermeidet wiederholte Datenbankzugriffe innerhalb derselben Session. 
- *Beispiel*: Wird eine Entität mehrfach abgefragt, liefert der Cache sofort das Objekt. 
### Second-Level Cache: 
- Scope: Anwendung oder SessionFactory.
- Muss explizit konfiguriert werden, z.B. mit Ehcache, Infinispan oder Hazelcast. 
- *Vorteil*: Reduziert Datenbankzugriffe über Sessions hinweg. 
- *Nachteil*: Zusätzlicher Speicherbedarf, Konfigurationsaufwand. 
### Query Cache
- Speichert Ergebnisse wiederholter Queries. 
- Speichert Ergebnisse von Queries, nicht die Entitäten selbst. 
- *Vorteil*: Besonders nützlich bei wiederholten, identischen Abfragen. 
- *Nachteil*: Änderungen an den Entitäten erfordern invalidierte oder aktualisierte Cache-Einträge.