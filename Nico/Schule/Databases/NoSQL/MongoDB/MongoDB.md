---
Fach: "[[DB]]"
Thema:
  - "[[Schule/Databases/NoSQL/NoSQL|NoSQL]]"
---
>Ist ein Document Store
# Vorteile
---
- Anwendungen mit sich schnell ändernden Datenanforderungen Projekte
- die horizontal skaliert werden müssen
- Echtzeitanalysen und Hochgeschwindigkeitsprotokollierung
- Content-Management-Systeme und Kataloge
- Mobile und soziale Infrastruktur
# Features
---
**Dokumentenorientierte Speicherung**
MongoDB speichert Daten in BSON-Dokumenten (Binary JSON), die unterschiedliche Strukturen und Felder haben können. 
**Flexibles Schema**
Dokumente in derselben Sammlung können unterschiedliche Felder haben, was eine einfache Anpassung an sich ändernde Datenanforderungen ermöglicht. 
**Skalierbarkeit**
MongoDB unterstützt horizontale Skalierung durch Sharding, wobei Daten auf mehrere Server verteilt werden. 
**Hohe Leistung**
Mit Unterstützung für Indizierung und Aggregation bietet MongoDB schnelle Abfrageausführung und Datenverarbeitungsfunktionen. 
**Umfangreiche Abfragesprache**
MongoDB bietet eine leistungsstarke Abfragesprache, die komplexe Abfragen unterstützt, darunter Textsuche und georäumliche Abfragen. 
**Replikation und hohe Verfügbarkeit**
MongoDB unterstützt Replikatsätze, wodurch Datenredundanz und hohe Verfügbarkeit gewährleistet werden.
# Schema Design
----
**Einbetten vs. Referenzieren**
Entscheiden Sie, ob Sie verwandte Daten in ein Dokument einbetten oder Referenzen zu separaten Sammlungen verwenden möchten. 
**Vermeiden Sie tiefe Verschachtelungen**
Begrenzen Sie die Tiefe verschachtelter Dokumente, um Leistungsprobleme zu vermeiden.
**Denormalisierung** 
Duplizieren Sie Daten bei Bedarf, um die Leseleistung zu verbessern, aber beachten Sie dabei die Komplexität der Aktualisierung. 
**Modellieren Sie Eins-zu-Viele-Beziehungen**
Verwenden Sie Arrays für kleine Gruppen verwandter Elemente oder separate Sammlungen für große Gruppen. 
**Berücksichtigen Sie das Wachstum von Dokumenten**
Lassen Sie Platz für das Wachstum von Dokumenten, um häufige Umzüge zu vermeiden.
## Beispiele
### 1:N wenige (Eingebettete Dokumente)
```json
{ 
	"_id": ObjectId("..."), 
	"name": "Max Mustermann", 
	"email": "max@ts.de", 
	"adressen": [ 
		{ 
			"type": "privat", 
			"strasse": "Leopoldstr. 101 a", 
			"stadt": "München", 
			"bundesland": 
			"Bayern", 
			"plz": "81401"
		}, 
		{ 
			"type": "arbeit", 
			"strasse": "Leopoldstr. 101 b", 
			"stadt": "München", 
			"bundesland": "Bayern", 
			"plz": "81401" 
		} 
	] 
}
```
### 1:N viele (Beziehungen zu andern Dokumenten)
```json
{ 
	"_id": ObjectId("a"), 
	"name": "Paula Schmidt", 
	"email": "paula@schmidt.de" 
}
```

```json
{ 
	"_id": ObjectId("b"), 
	"kunde_id": ObjectId("a"), // Beziehung zu Kunde 
	"bestelldatum": ISODate("2023-04-15"), 
	"gesamt": 99.99 
}
```
# Indizierung
---
## Typen von Indizes
- **Index über ein Feld**: Verbessert Abfragen in einem einzelnen Feld. 
- **Zusammengesetzter Index**: Verbessert Abfragen in mehreren Feldern. 
- **Multikey-Index**: Indiziert Arrays und erstellt einen Indexeintrag für jedes Array-Element. 
- **Textindex**: Unterstützt Textsuchabfragen für Zeichenfolgeninhalte. 
- **Geodatenindex**: Optimiert Abfragen für Geodatenkoordinaten. 
- **Hash-Index**: Indiziert den Hashwert eines Feldes.
### Beispiele
```python
collection.create_index("feldname")
collection.create_index([("field1", 1), ("field2", -1)])
```
## Optionen für Indizes
- **unique**: Stellt sicher, dass die indizierten Felder eindeutige Werte haben. 
- **sparse**: Indiziert nur Dokumente, die das indizierte Feld enthalten. 
- **expireAfterSeconds**: Entfernt Dokumente nach einer bestimmten Anzahl von Sekunden automatisch (TTL-Index).
### Beispiele
```python
collection.create_index("email", unique=True) 
collection.create_index("last_login", expireAfterSeconds=2592000) # 30 days
```
## Regeln für Indizes
- Erstellen Sie Indizes, um Ihre Abfragen zu unterstützen. 
- Verwenden Sie zusammengesetzte Indizes für Abfragen mit mehreren Bedingungen. 
- Vermeiden Sie die Erstellung unnötiger Indizes, da diese Schreibvorgänge verlangsamen. 
- Überwachen Sie die Indexnutzung und entfernen Sie nicht verwendete Indizes.
- Berücksichtigen Sie die Auswirkungen von Indizes auf die Schreibleistung.