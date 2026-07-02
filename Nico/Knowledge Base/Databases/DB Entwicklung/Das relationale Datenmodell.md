---
Thema:
  - "[[Relational Databases]]"
---
**Beispiel**
![[Pasted image 20260606181835.png]]
# Definition einer Tabelle (Relation)
---
- eindeutiger Name
- kann mehrere Spalten haben
- keine bis unendlich Datensätze (Tupel)
- ein Wert pro Attribut pro Datensatz
- hat einen Primärschlüssel
# Darstellungen von Tabellen
---
## Graphisch
![[Pasted image 20241106010305.png]]
Mitglied ist Name der Tabelle
M_Nr ist Primary Key
Vorname, Nachname und Geburtstag sind Attribute
## Mengenschreibweise
`Mitglied: { [ M_Nr : integer, Vorname : string, Nachname : string, Geburtstag : date ]}`
## Regeln
- Der Primary Key wird unterstrichen und daneben wird PK geschrieben
- Neben Foreign Keys wird FK geschrieben
- N:M Beziehungen werden in 2 1:N Beziehungen mit einer Linktabelle aufgelöst (Linktabelle = N Seite)
- FKs immer auf die N Seite
- Attribute von Beziehungen kommen in die Link Tabelle

# Anzahl möglicher Datensätze
---
>Mögliche Datensätze sind Kombinationen aus den Wertebereichen der einzelnen Attribute
### Formel
>dom bedeutet Domäne, also die Anzahl der möglichen Werte

dom(A1) x dom(A2) x dom(A$n$)
# Wichtige Konzepte eines RDBMS
---
### Datenunabhängigkeit 
eigene Datenhaltungsschicht, logisches Schema, unabhängig von physikalischer Speicherung 
### Benutzerfreundlichkeit 
einfach zu erlernen, leichte Handhabung 
### Mehrfachzugriff 
gleichzeitige Nutzung der Daten 
### Flexibler Zugriff 
sequenziell, wahlfrei, mehrdimensional 
### Effizienz 
Schnelle Verarbeitung, schnelle Antwortzeiten 
### Zugriffsschutz 
Berechtigungssystem für Benutzerzugriffe 
### Sicherheit gegen Datenverlust 
Replikation, Backup 
### Datenintegrität 
Normalisierung, referenzielle Integrität, typisierte Speicherung
# Zusammenhang zwischen semantischem Modell und Datenmodell der 3. Normalform
---
**Semantisches Modell**
In Fließtext o.ä. beschriebene Art der Daten
**3. Normalform**
[[Normalisierung|Normalisierte]] Form der Daten
# Architektur einer 3-Schicht Datenbankanwendung
---
![[Pasted image 20260407190657.png]]

# Beispiele für RDBMS
---
- MySQL
- Microsoft SQL Server
- PostgreSQL
- SQLite
