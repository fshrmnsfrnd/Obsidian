---
Thema:
  - "[[MySQL]]"
---
>Bei einem Volltextindex wird aus allen Wörtern des Textes eine Wort-Liste erstellt. Zu jedem Wort in der Liste wird die Datensatz-Id vermerkt in dem das Wort vorkommt. Kurze Wörter (Länge < 4) werden in der Regel ignoriert. Die Länge kann in den Datenbankeinstellungen oft geändert werden.

# Beispiel
---
### Datensätze
| id  | memo                                   |
| --- | -------------------------------------- |
| 1   | Algorithmen, Datenbanken               |
| 2   | Algorithmen und Design Patterns        |
| 3   | Datenbanken-Entwurf, [[Stored Procedures]] |
| ... | ...                                    |
### Volltextindex
| Wort        | id   |
| ----------- | ---- |
| Algorithmen | 1,2  |
| Datenbanken | 1, 3 |
| Design      | 2    |
| Procedures  | 3    |
| ...         | ...  |
# Erstellen
---
### Neue Tabelle
```sql
CREATE TABLE table( 
	id INT AUTO_INCREMENT PRIMARY KEY, 
	... 
	memo TEXT, 
	FULLTEXT INDEX idx_full_memo(memo) 
) ENGINE=InnoDB;
```
### Existierende Tabelle
```sql
ALTER TABLE table ADD FULLTEXT INDEX idx_full_colName(colName);
```
# In Abfragen verwenden
---
Die Suchbegriffe werden mit Leerzeichen getrennt als Parameter an ``AGAINST`` übergeben.
`MATCH` liefert für jeden Datensatz eine Fließkommazahl. Sie ist umso höher, je relevanter der Datensatz ist und je häufiger der Suchbegriff gefunden wurde.

```sql
SELECT id, MATCH(memo) AGAINST ('Design') AS treffer 
FROM table 
HAVING treffer > 0.5 
ORDER BY treffer DESC
```

> [!NOTE] 
> Die Filterung wird mittels HAVING durchgeführt; wie bei Gruppierungs-Funktionen ist keine Filterung mit den Schlüsselwort WHERE möglich.
## Boolean Mode
```sql
SELECT 
	id, 
	MATCH(memo) AGAINST('+Design Datenbank* -Procedures' IN BOOLEAN MODE) AS treffer FROM mitglied 
HAVING treffer > 0.5 
ORDER BY treffer DESC
```
### Ausdrücke
| Ausdruck           | Erklärung                                                                |
| ------------------ | ------------------------------------------------------------------------ |
| `Wort`             | Das Wort *sollte* enthalten sein.                                        |
| `+Wort`            | Das Wort *muss* enthalten sein.                                          |
| `-Wort`            | Das Wort *darf nicht* enthalten sein.                                    |
| `<Wort`            | Das Wort hat ein *geringeres Gewicht* als die anderen Wörter             |
| `>Wort`            | Das Wort hat ein *höheres Gewicht* als die anderen Wörter.               |
| `Wort*`            | Das Wort *beginnt* mit den angegebenen Buchstaben.                       |
| `"Wort1 Wort2"`    | Die *Wortfolge* muss exakt so sein: Wort1 Wort2                          |
| `"Wort1 Wort2" @5` | Der *Abstand* zwischen Wort1 und Wort2 darf *maximal* 5 Wörter betragen. |
