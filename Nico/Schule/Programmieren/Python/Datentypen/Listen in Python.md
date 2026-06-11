---
Fach: "[[Programmieren]]"
tags:
Thema:
  - "[[Python]]"
---
Listen sind Daten die in einer Festen Reihenfolge gespeichert werden. Da diese Reihenfolge fix ist kann auf die Daten über den sogenannten **Index** zugegriffen werden, dabei gilt:  
- Die Länge der Liste muss **nicht** angegeben werden  
- In einer Liste können unterschiedliche Datentypen verwendet werden  

```python
liste1: list = []
liste2: list = ["str", 1, "Baum"]
liste3: list[str]
```
## Zugriff über Index
```python
print(liste1[0]) # Ausgabe: 1
print(liste1[-1]) # Ausgabe: 3
```
## Zugriff auf Teilliste
```python
print(liste2[1:3]) # Ausgabe: ["ist", "eine"]
print(liste2[:2])  # Ausgabe: ["Das", "ist"]
print(liste2[2:])  # Ausgabe: ["eine", "Liste"]
   
print(liste2[0:2:2]) # Ausgabe: ["ist"]
```
## Kombination von Listen
```python
print(liste2 + liste4) 
# Ausgabe: ["Das", "ist", "eine", "Liste", "str", 1, "Baum"]
```  

## Listenmethoden

| Funktion    | Beschreibung                            | Beispiel                   |
| ----------- | --------------------------------------- | -------------------------- |
| `append()`  | Element an eine Liste anhängen          | `liste1.append("Text")`    |
| `extend()`  | Liste an eine Liste anhängen            | `liste1.extend([1, 2, 3])` |
| `insert()`  | Element an bestimmter stellen anfügen   | `liste1.insert(3, "Text")` |
| `pop()`     | Element an bestimmter stelle löschen    | `liste1.pop(2)`            |
| `remove()`  | Daten aus liste löschen                 | `liste1.remove("Text")`    |
| `reverse()` | Reihenfolge der Liste umdrehen          | `liste1.reverse()`         |
| `sort()`    | Liste sortieren                         | `liste1.sort()`            |
| `len()`     | Anzahl an Elmente in der Liste bekommen | `liste1.len()`             |
| `max()`     | Größtes Element einer Liste             | `liste1.max()`             |
| `min()`     | Kleinstes Element einer Liste           | `liste1.min()`             |
