---
Thema:
  - "[[Python]]"
---

| Beschreibung                        | Datentyp | Beispiel                      |
| ----------------------------------- | -------- | ----------------------------- |
| Ganze Zahlen                        | int      | 1                             |
| Komma Zahlen                        | float    | 4.5                           |
| komplexe Zahlen                     | complex  | 3+ 4j                         |
| Boolsche Werte                      | bool     | True                          |
| [[Strings in Python]]                         | str      | "Hallo"                       |
| [[Listen in Python]]                           | list     | ["Kaffee", "Milch", "Zucker"] |
| [[Tupel]]                           | tuple    | ("Kaffee", "Milch", "Zucker") |
| [[Dictionary in Python]] (assoziatives Array) | dict     | {"name": "John", "later": 44} |
| [[Heap]]                            | heapq    |                               |
| [[Queues in Python]]                           | deque    |                               |

# Variablen
Variablen erhalten in Python ihren Datentypen automatisch zugeordnet. Dabei ist dieser Datentyp auch nicht fix und kann jeder Zeit geändert werden. Dadurch existiert in Python per default **KEINE** typesafety.  
```python
# Einfache Zuweisungen
text = "Python"
y = 2

# Mehrere Variablen gleichzeitig Zuweisen
x, y, z = "Baum", 3, "Kuchen"

# Angeben eines Typen
x = str("Text")
y = int(3)
 
# Typumwandlungen (das Programm crashed wenn es nicht möglich ist)
text = "3"
z = float(text)
```

## Konstanten
Tatsächliche Konstanten gibt es in Python nicht, um Konstanten zu kennzeichnen beginnt der Variablenname mit einem `_`.