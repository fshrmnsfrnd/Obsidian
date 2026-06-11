---
Fach: "[[DB]]"
Thema:
  - "[[Databases]]"
---
# Kategorien von NoSQL
---
## Key/Value
**Daten**
Key/Value Pairs
**Keys**
Namen, Attribute
**Werte**
Strings, Hashes, Listen
**Vorteile**
einfaches Modell
**Nachteile**
Abfragesprache oft sehr eingeschränkt
## Document Store
**Daten**
Informationen werden als Datei/Dokument abgelegt
**Dokument**
z.B. json, yaml, bson, rdf
**Identifizierung**
Jedes Dokument hat eine ID
**Vorteil**:
Die Verantwortung für das Dokumenten-Schema liegt in der Anwendung. Erweiterungen sind kein Problem 
**Nachteil**
keine referenzielle Integrität, keine Normalisierung.
## Wide Column Store
**Daten**
spaltenorientiert, also pro Attribut eine Tabelle
**Vorteil**
gute Analyse und einfache Aggregation der Daten, Verwendung in OLAP- und Data-Warehouse- Umgebungen. 
**Nachteil**
Suchen und Einfügen von Daten ist aufwendiger
## Graph Datenbank
- Speicherung von Informationen erfolgt in **Knots** und **Edges** 
- Property-Graphen bieten die Möglichkeit, Knots und Edges Attribute zu geben
- Anwendungsbereiche: Graphen, semantische Netzwerke und Location Bases Services (Smartphones)
# Konzepte von NoSQL
---
### Datenmodell ist nicht relational 
Keine Speicherung in herkömmlichen Tabellen 
### Datenbank ist schemafrei 
oder hat nur schwächere Schemarestriktionen 
### verteilte Systeme 
einfache Replikationsmechanismen 
### horizontale Skalierbarkeit 
Server-Cluster 
### einfache API 
### Open Source
# Motivation für NoSQL
---
### Skalierbarkeit
- **Horizontale Skalierung:** Hinzufügen/Entfernen von Servern je nach Bedarf
- **Problem bei relationalen DBs:** Horizontale Skalierung schwierig, oft nur vertikale Skalierung möglich
- **NoSQL-Vorteil:** Automatische Anpassung an Cluster-Änderungen ohne Administratoreingriff
### Kosten
- Relationale DBs: Teure Lizenzen (nach Servergröße, Benutzerzahl)
- **NoSQL-Vorteil:** Viele als Open Source verfügbar, kommerzielle Support-Services optional
### Flexibilität
- **Problem bei relationalen DBs:** Festes Schema erforderlich, alle Tabellen/Spalten müssen vorab definiert sein
- **Beispiel:** E-Commerce mit verschiedenen Produktkategorien erfordert separate Tabellen
- **NoSQL-Vorteil:** Dynamisches Hinzufügen von Attributen ohne Schemaänderung möglich
### Verfügbarkeit
- **NoSQL-Vorteil:** Cluster-Architektur mit mehreren Servern – bei Ausfall eines Servers übernehmen andere
- **Problem bei relationalen DBs:** Single-Server-Betrieb führt bei Ausfall zu Totalausfall (ohne Backup-Server)

**Fazit:** NoSQL-Datenbanken bieten bessere Lösungen für moderne, datenintensive Anwendungen mit hohen Verfügbarkeitsanforderungen.
# Konzepte
---
## Quorum
### Definition
- **Quorum** = Mindestanzahl an Servern, die auf Lese-/Schreibvorgang antworten müssen
- Vorgang gilt erst als *abgeschlossen*, wenn Quorum erreicht
### Funktionsweise
**Normalbetrieb:**
- Alle Server haben **konsistente Daten**
**Während Replikation:**
- Daten werden von Server zu Server kopiert
- Replika-Server können *inkonsistente Daten* aufweisen
### Lesevorgänge mit Quorum

| Aspekt | Beschreibung |
| --- | --- |
| **Abfrage** | Alle Server mit gespeicherten Daten werden abgefragt |
| **Zählung** | Anzahl unterschiedlicher Antwortwerte wird ermittelt |
| **Rückgabe** | Wert, der konfigurierbaren Schwellenwert erreicht/überschreitet |
> [!info] Schwellenwert-Kompromiss
> - **Niedriger Schwellenwert** (z.B. 1): Schnelle Antwort, **höheres Risiko** für inkonsistente Daten
> - **Hoher Schwellenwert**: Langsamere Antwort, **geringeres Risiko** für Inkonsistenzen

 ![[Pasted image 20260407193451.png]]

## CAP-Theorem
### Definition
- **Eric Brewer's Theorem**: Verteilte Datenbanken können **nicht gleichzeitig** alle drei Eigenschaften erfüllen
- Trade-off zwischen den drei Dimensionen erforderlich
### Die drei Eigenschaften

| Eigenschaft             | Bedeutung                                                           |
| ----------------------- | ------------------------------------------------------------------- |
| **C**onsistency         | Konsistente Kopien auf verschiedenen Servern                        |
| **A**vailability        | Antwort auf jede Abfrage bereitstellen                              |
| **P**artition Tolerance | Bei Netzwerkausfall bleiben Server mit konsistenten Daten verfügbar |
![[Pasted image 20260412133935.png]]
## ACID vs. BASE
### Konzept-Übersicht

| Aspekt          | ACID                | BASE                   |
| --------------- | ------------------- | ---------------------- |
| **Einsatz**     | Relationale DBMS    | NoSQL-Datenbanksysteme |
| **Fokus**       | Konsistenz          | Verfügbarkeit          |
| **CAP-Theorem** | Konsistentes System | Hohe Verfügbarkeit     |

![[Pasted image 20260407193602.png]]

### CAP-Theorem Kontext
> [!info] Unmöglichkeit
> Kein partitionstolerantes verteiltes System kann **gleichzeitig** Konsistenz UND Verfügbarkeit erreichen

**Partitionstoleranz:** System funktioniert bei vorübergehenden Kommunikationsausfällen
### ACID – Relationale Datenbanken
#### Eigenschaften

| Eigenschaft | Englisch | Bedeutung |
| --- | --- | --- |
| **A** | Atomicity | Alles-oder-nichts-Eigenschaft |
| **C** | Consistency | Konsistenter Datenbankzustand |
| **I** | Isolation | Keine gegenseitige Beeinflussung |
| **D** | Durability | Dauerhafte Speicherung |
#### Details
**Atomarität:**
- Transaktion = Folge von Datenbank-Operationen
- Wird *entweder ganz* oder *gar nicht* ausgeführt
**Konsistenz:**
- Konsistente DB vor Transaktion → Konsistente DB nach Transaktion
**Isolation:**
- Nebenläufige Transaktionen beeinflussen sich *nicht gegenseitig*
**Dauerhaftigkeit:**
- Daten nach erfolgreichem Abschluss **garantiert dauerhaft** gespeichert
- Garantie gilt auch bei Systemfehlern (Software/Hardware)
### BASE – NoSQL-Datenbanken
---
#### Eigenschaften

| Eigenschaft | Englisch             | Bedeutung                      |
| ----------- | -------------------- | ------------------------------ |
| **BA**      | Basically Available  | Verfügbarkeit garantiert       |
| **S**       | Soft State           | Zustand während Replikation    |
| **E**       | Eventual Consistency | Konsistenz irgendwann erreicht |
#### Details
**Basically Available:**
- Antwort auf *jede Anfrage* garantiert
- Möglicherweise **inkonsistente Antworten**

**Soft State:**
- Datenänderung wird erst nach Replikationsabschluss zu *Fakt*
- Hängt mit Eventual Consistency zusammen

**Eventual Consistency:**
- System wird **irgendwann** konsistent sein
- Keine sofortige Konsistenz-Garantie

$$\text{ACID} \rightarrow \text{Konsistenz} \quad | \quad \text{BASE} \rightarrow \text{Verfügbarkeit}$$