---
Fach: "[[DB]]"
Thema:
  - "[[Python]]"
  - "[[Schule/Databases/NoSQL/MongoDB/MongoDB|MongoDB]]"
---
# Query One
```python
doc = collection.find_one({"name": "Max Mustermann"}) 
print(doc)
```
# Query Many
```python
cursor = collection.find({"alter": {"$gt": 25}}, {"alter": 1, "name": 0})
for doc in cursor: 
	print(doc)
```
`1` und  `0` sagt  ob ein Attribut angezeigt werden soll oder nicht
# Query Operations
---
## Operators

| Ausdruck | Beschreibung         | Beispiel                        |
| -------- | -------------------- | ------------------------------- |
| `$eq`    | equals               | `{"qty": {"$eq": 50}}`          |
| `$ne`    | not equal            | `{"status": {"$ne": "A"}}`      |
| `$gt`    | Greater Than         | `{"qty": {"$gt": 50}}`          |
| `$gte`   | Greater or Equal     | `{"qty": {"$gte": 50}}`         |
| `$lt`    | Lower Than           | `{"qty": {"$lt": 50}}`          |
| `$lte`   | Lower Than or Equals | `{"qty": {"$lte": 50}}`         |
| `$in`    | in List              | `{"qty": {"$in": ["A", "B"]}}`  |
| `$nin`   | Not in List          | `{"qty": {"$nin": ["A", "B"]}}` |

```python
collection.find({"age": {"$gt": 25, "$lte": 35}})
```
## Logical Operators
### OR
```python
inventory.find({
    "$or": [
        {"status": "A"},
        {"qty": {"$lt": 30}}
    ]
})
```
### AND
```python
inventory.find({
    "status": "A",
    "qty": {"$lt": 30}
})

# AND and OR combined:
inventory.find({
    "status": "A",
    "$or": [
        {"qty": {"$lt": 30}},
        {"item": {"$regex": "^p"}}
    ]
})
```
## Regex
```python
cursor = collection.find({"name": {"$regex": "^J"}})
```
## Exists / Null

> [!NOTE] `None` in Python = `null` in MongoDB

```python
students.insert_one({"name": "Tom", "phone": None})

query = {"$or": [{"phone": None}, {"phone": {"$exists": False}}]} 
# entweder null oder Feld fehlt
for doc in students.find(query):
    print("☎️", doc)
```
# Cursor
---
>`collection.find({})` gibt einen Cursor zurück
```python
cursor = inventory.find({})
try:
    for doc in cursor:
        # Code
finally:
    cursor.close()
# oder
with inventory.find() as cursor:
    for doc in cursor:
        print(f"- {doc['item']}")
```
## Sortieren
```python
collection.find().sort("alter", -1) #Absteigend
collection.find().sort("alter", 1) #Aufsteigend
# ODER
from pymongo import ASCENDING, DESCENDING
collection.find().sort("alter", DESCENDING) #Absteigend
collection.find().sort("alter", ASCENDING) #Aufsteigend

# Sortieren nach mehreren Feldern
collection.find().sort([
    ("status", ASCENDING),
    ("qty", DESCENDING) # Nur bei gleichem Status
])
```
## Limit
```python
collection.find().limit(5) # gibt die ersten 5 zurück. Kann auch mit .sort() kombiniert werden
collection.find().sort("alter", -1).limit(5) # Gibt die ältesten 5 aus
```
## Skip
```python
collection.find().skip(3) # überspringt die ersten 3, ausgabe ab dem 4. Dokument
```
## Seitenweise (Pagination)
```python
def hole_seite(seiten_nummer, pro_seite=2):
    skip_anzahl = (seiten_nummer - 1) * pro_seite
    ergebnis = inventory.find().skip(skip_anzahl).limit(pro_seite)
    return list(ergebnis)

print("\nSeite 1:")
for dok in hole_seite(1, 2):
    print(f"- {dok['item']}")

print("\nSeite 2:")
for dok in hole_seite(2, 2):
    print(f"- {dok['item']}")
```
# Count Documents
```python
# Genaue Anzahl
inventory.count_documents({})
# Geschätzte Anzahl (Nur Anzahl aller Dokumente in der Collection)
inventory.estimated_document_count()
```
# Distinct Values
```python
inventory.distinct("s") # findet aus den Documents {"s": "A"}, {"s": "B"}, {"s": "B"} 
# ["A", "B"]
```
# Typumwandlungen
```python
# Liste
ergebnis_liste = list(inventory.find({"status": "A"}))
# Dictionary
mengen_dict = {
    doc['item']: doc['qty']
    for doc in inventory.find()
}
```
# Embedded Documents
```python
kurse.find({
	"studenten.note": {"$lt": 2.0}
	"studenten.name": "Alice"
})

# EXAKT. Auch die Reihenfolge muss stimmen
inventory.find({
    "size": {"h": 14, "w": 21, "uom": "cm"}
})
```
# Arrays
```python
# Array enthält den Wert
inventory.find({"tags": "red"}) #Findet ['blank', 'red']
# Array enthält alle Werte
inventory.find({
    "tags": {"$all": ["red", "blank"]} # findet ['red', 'blank', 'plain']
})
# Exakt diese Tags in dieser Reihenfolge
inventory.find({
    "tags": ["blank", "red"]
})
# Length abfragen
inventory.find({
    "tags": {"$size": 3} # findet Array die 3 lang sind
})
```
# Gruppieren
```python
pipeline = [{
	"$group": {
	     "_id": "$attribute", # Group key. Mit $ wird nach dem Value des Fields gruppiert
		"<fieldToShow>": { 
			"<functionName e.g. sum>" : "<expression e.g. 1>" 
		},
	}
}]
for group in students.aggregate(pipeline):
    print(group)
# Es wird nach eingeschrieben gruppiert und dann pro Gruppe der Count Wert gezeigt
```
# Lookup (Join)
```python
pipeline = [
    {
        "$lookup": {
            "from": "noten",
            "localField": "_id", #Aus Input Collection
            "foreignField": "student_id", #Aus from
            "as": "student_kurse"
        }
    }
]

for result in students.aggregate(pipeline):
    print(result)
```
# Ausgabe
---
## Formatierte Ausgabe
```python
from pprint import pprint
for dok in inventory.find():
    pprint(dok)
    print("-" * 50) # Eine Zeile mit 50 -
```
## Auf Attribute zugreifen
```python
for doc in cursor:
	print(f"- {doc['item']}: Menge {doc['qty']}")
```
## Nur bestimmte Felder ausgeben
```python
# Felder auswählen
inventory.find(
    {"status": "A"},
    {"item": 1, "status": 1} #_id wird trotzdem ausgegeben
)
# Felder ausschließen (Sind nur ausgeschlossene Felder dabei, werden alle anderen angezeigt)
inventory.find(
    {"status": "A"},
    {"item": 1, "status": 1, "_id": 0} #_id wird nicht ausgegeben
)
# Verschachtelte Felder
inventory.find(
    {},
    {"item": 1, "size.uom": 1, "_id": 0}
)
```
