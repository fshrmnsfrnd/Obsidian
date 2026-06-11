---
Fach: "[[Programmieren]]"
tags:
Thema:
  - "[[Python]]"
---
# Dictionaries
Dictionaries sind eine Sammlung von Key-Value Paaren. Die Keys sind entweder vom Datentyp `int` oder `str`, die Values können jeden Datentypen annehmen. Man kann über den Key auf sie Zugreifen: 
```python
      dict1 = {"name": "Hans", "alter": 34}
      print(dict1["name"]) # Ausgabe: Hans
      
      # Prüfen ob ein Key Vorhanden ist
      if "name" in dict1:
        	print(dict1["name"])
          
      # Element hinzufügen
      dict1["nachname"] = "Mayer"
```

## Dictionarymethoden

| Funktion   | Beschreibung                                                        | Beispiel                               |
| ---------- | ------------------------------------------------------------------- | -------------------------------------- |
| `len()`    | Ausgabe der Elemente                                                | `len(dict1)`                           |
| `clear()`  | Löscht alle Elemente                                                | `dict1.clear()`                        |
| `copy()`   | Erzeugt eine Kopie vom Dictionary                                   | `dict1.copy()`                         |
| `get()`    | Gibt den wert vom key zurück wenn er existiert ansonsten default    | `dict1.get("name", "NN")`              |
| `keys()`   | Gibt eine Liste mit allen Keys aus                                  | `dict1.keys()`                         |
| `pop()`    | Löscht ein Key und gibt den Wert zurück                             | `dict1.pop("name", "Kein name")`       |
| `update()` | Ergänzt das Dictionary                                              | `dict1.update({"adresse": "München"})` |
| `values()` | Gibt eine Liste mit allen Values zurück                             | `dict1.values()`                       |
| `items()`  | Wandelt jedes Key value paar in ein Tupel (hilfreich bei Schleifen) | `dict1.items()`                        |
