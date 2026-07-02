---
Thema:
  - "[[MySQL]]"
---
# Mathematische Operatoren
---

| SQL | Beschreibung                                                  |
| --- | ------------------------------------------------------------- |
| `+`   | Addition                                                      |
| `-`   | Subtraktion                                                   |
| `*`   | Multiplikation                                                |
| `/`   | Division                                                      |
| `%`   | Modulo-Operator. Ermittlung des Rests einer Ganzzahldivision. |
# Vergleichs Operatoren
---

| SQL       | Beschreibung        |
| --------- | ------------------- |
| `=`         | GLEICH              |
| `<`         | KLEINER als         |
| `<=`        | KLEINER oder GLEICH |
| `>`         | GRÖSSER         |
| `>=`        | GRÖSSER oder GLEICH |
| `<>`        | UNGLEICH            |
# Logische Operatoren
---

| SQL | Beschreibung   |
| --- | -------------- |
| `AND` | Logisches UND  |
| `OR`  | Logisches ODER |
# Weitere nützliche Operatoren
---

| SQL                        | Beschreibung                                                                                                                                                              |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `NOT`                      | Negation oder Verneinung                                                                                                                                                  |
| `IS NULL`                  | Prüft, ob die Spalte KEINEN Inhalt hat.                                                                                                                                   |
| `NOT IS NULL`              | Prüft, ob die Spalte irgendeinen Inhalt hat.                                                                                                                              |
| `LIKE`                     | Mustervergleich mit Texten im Zusammenhang mit JOKER-Zeichen % : beliebige Anzahl unbekannter Zeichen oder JOKER-Zeichen _: Ersatz für ein unbestimmtes Zeichen           |
| `BETWEEN X AND Y`          | Alle Werte im Intervall X bis Y inklusive X und Y.                                                                                                                        |
| `IN (Werte-Liste)`         | Prüft, ob der Feldwert in der Werte-Liste ist. (Häufig bei [[Subquerys#Nicht korrelierte Unterabfrage\|nicht-korrelierten Unterabfragen]])                |
| `NOT IN (Werte-Liste)`     | Prüft, ob der Feldwert NICHT in der Werte-Liste ist. (Häufig bei [[Subquerys#Nicht korrelierte Unterabfrage\|nicht-korrelierten Unterabfragen]])          |
| `EXISTS (Werte-Liste)`     | Prüft, ob für ein Wert in einer Liste von Datensätzen vorhanden ist (Häufig bei [[Subquerys#Korrelierte Unterabfrage\|korrelierten Unterabfragen]])       |
| `NOT EXISTS (Werte-Liste)` | Prüft, ob für ein Wert NICHT in einer Liste von Datensätzen vorhanden ist (Häufig bei [[Subquerys#Korrelierte Unterabfrage\|korrelierten Unterabfragen]]) |
