---
Thema:
  - "[[Python]]"
  - "[[MongoDB]]"
---
# Installieren
---
```bash
pip install pymongo
```
# Verbindung herstellen
---
```python
from pymongo import MongoClient 

# Herstellen der Verbindung über Standard-host und -port 
client = MongoClient('mongodb://localhost:27017/[database?[authSource=???][,replicaSet=???][,ssl=???][,connectionTimeoutMS=???]]' [, maxPoolSize=50])

# alternativ über den Konstruktor der Klasse MongoClient
client = MongoClient('localhost', 27017) 

# Zugriff auf die Datenbank meineDB 
db = client['meineDB'] 

# Zugriff auf eine Collection 
collection = db['meineCollection']
```
# Insert
---
### Insert One
```python
result = collection.insert_one({"name": "Max Mustermann", "alter": 30}) 
print(f"Inserted document ID: {result.inserted_id}")
```
### Insert Many
```python
documents = [
	{"name": "Max", "alter": 25}, 
	{"name": "Paula", "alter": 35} 
] 
result = collection.insert_many(documents) 
print(f"Inserted document IDs: {result.inserted_ids}")
```
# Update
---
### Update One
```python
result = collection.update_one(
	{"name": "Max Mustermann"}, 
	{"$set": {"alter": 31}} 
)
print(f"Geändert {result.modified_count} document(s)")
```
### Update Many
```python
result = collection.update_many(
	{"alter": {"$lt": 30}}, 
	{"$inc": {"alter": 1}} 
) 
print(f"Modified {result.modified_count} document(s)")
```
# Delete
---
### Delete One
```python
result = collection.delete_one({"name": "Max Mustermann"}) 
print(f"Gelöscht wurden {result.deleted_count} Dokument(e)")
```
### Delete Many
```python
result = collection.delete_many({"age": {"$gte": 40}}) 
print(f"Gelöscht wurden {result.deleted_count} Dokument(e)")
```
# Bulk
---
>Bulk Operationen verbessern die Schreibgeschwindigkeit

```python
from pymongo import InsertOne, UpdateOne, DeleteOne 
operations = [ 
	InsertOne({"name": "Max", "alter": 28}), 
	UpdateOne({"name": "Paula"}, {"$set": {"alter": 26}}), 
	DeleteOne({"name": "Moritz"}) 
] 
result = collection.bulk_write(operations) 
print(f"Eingefügt: {result.inserted_count}, geändert: {result.modified_count}, gelöscht: {result.deleted_count}")
```
# ObjectId
---
>Jedes Dokument hat eine Id vom Typ `ObjectId`
### Import
```python
from bson import ObjectId
```
### Id aus Dokument holen
```python
doc = students.find_one()
id_str = str(doc["_id"])
```
### Dokument nach Id suchen
```python
found = students.find_one({"_id": ObjectId(id_str)})
print("Gefunden per ObjectId:", found)
```

