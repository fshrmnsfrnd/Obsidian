---
Thema:
  - "[[MySQL]]"
---
Ein Block hat zwei unterschiedliche Aufgaben:
- Verwandte Codesegmente und Anweisungen werden **logisch gruppiert**.
- Der **Gültigkeitsbereich** von Variablen und anderen Objekten kann gesteuert werden
# Struktur
---
Immer folgende Reihenfolge:
1. Variablen- und Bedingungsdeklarationen
2. Cursor-Deklarationen
3. Handler-Deklarationen
4. Programmcode
# Labels
---
```sql
myLabel:BEGIN 
	Variablen-Deklarationen
	Cursor-Deklarationen
	Handler-Deklarationen
	Anweisungen
END myLabel
```
- Lesbarkeit (BEGIN und END können einander zugeordnet werden)
- Block kann mit `LEAVE` verlassen werden
