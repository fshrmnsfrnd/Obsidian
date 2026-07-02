---
Thema:
  - "[[MySQL]]"
---
# Warum Views
---
- Sicherheit
	- Bestimmte Attribute können ausgeblendet werden
- Zweckmäßigkeit
	- Häufige Abfragen speichern
	- Datenbankstrukturen abstrahieren
## Vorteile von Views: 
- Views benötigen wenig **Speicherplatz**. 
- Views werden wie **Tabellen** verwendet. 
- **Berechnungen** und/oder komplexe JOINS werden gekapselt --> einfacher Zugriff durch die View. 
- Views können als **Zwischenschicht** zwischen den Tabellen und Anwendung eingesetzt werden. Änderungen der **Tabellenstruktur** wirken sich dann nicht direkt auf die externe Ebene aus. 
- Ausgewählten Benutzern oder Gruppen können **Zugriffsrechte** für Views erteilt werden. Damit kann der Zugriff auf Spalten und indirekt auch auf Datensätze eingeschränkt werden. 
## Nachteile von Views: 
- **Langsamer**: Erst wird der View analysiert und dann auf die Tabellen zugegriffen. 
- **Unbedachter Einsatz**: Möglicherweise wird die Komplexität von Benutzern unterschätzt.
# Views erstellen
---
```sql
CREATE VIEW viewName AS 
	SELECT Col1, Col2 
	FROM table1 
	WHERE Col = 'a';
```
# View ändern
---
```sql
ALTER VIEW viewName AS
	SELECT Col1, Col2 
	FROM table1 
	WHERE Col = 'b';
```
# Views löschen
---
```sql
DROP VIEW IF EXISTS viewName;
```
Daten werden dabei nicht gelöscht.
# View verwenden
---
```sql
SELECT col1, col2 FROM viewName;
```