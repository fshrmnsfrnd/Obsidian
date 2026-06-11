---
Fach: "[[DB]]"
Thema:
  - "[[Python]]"
  - "[[Schule/Databases/NoSQL/Redis/Redis|Redis]]"
---
**Command Reference**
https://redis.io/docs/latest/commands//
# Modul installieren
---
```cli
pip install redis
```
# Verbindung herstellen
---
```python
import redis  
# Verbindung zu Redis auf localhost  
redis_client = redis.Redis(host='localhost', port=6379, db=0, decode_responses=True)
# oder die Verwendung über eine connection URL  
redis_client = redis.from_url('redis://localhost:6379/0')
```
# Basic Operationen
---
```python
# Setzen eines String-Wertes  
redis_client.set('mein_key', 'Hallo, Redis!')  
# Einen String auslesen  
value = redis_client.get('mein_key')  
print(value.decode('utf-8')) # Ausgabe: Hallo, Redis!  
# einen string mit Ablaufzeit setzen (10 seconds)  
redis_client.setex('temp_key', 10, 'Ich werde in 10 Sekunden gelöscht.')  
# Einen numerischen Wert automatisch hochzählen  
redis_client.set('zähler', 0)  
redis_client.incr('zähler')  
# Ausgabe: 1  
print(redis_client.get('zähler'))
```
# List Operationen
---
```python
# Mehrere Elemente(Items) in eine Liste schreiben  
redis_client.lpush('meine_liste', 'item1', 'item2', 'item3')  
# Pop an item from the list  
item = redis_client.rpop('meine_liste')  
print(item.decode('utf-8')) # Ausgabe: item1  
# Get all items in the list  
items = redis_client.lrange('meine_liste', 0, -1)  
# Ausgabe: ['item3', 'item2']  
print([item.decode('utf-8') for item in items])
```
# Hash Operationen
---
>Ein Hash besteht aus einem Namen, der mehrere Felder hat
```python
# Hash-Felder setzen  
redis_client.hset('user:1', 'name', 'Max Mustermann')  
redis_client.hset('user:1', 'email', 'max.mustermann@ts.com')  
redis_client.hgetall('user:1)
# Ein Hash-Feld auslesen  
print(redis_client.hget('user:1', 'name').decode('utf-8')) # Ausgabe: Max Mustermann  
# Alle Hash-Felder auslesen  
user_data = redis_client.hgetall('user:1')  
print({k.decode('utf-8'): v.decode('utf-8') for k, v in user_data.items()})
```
# Set Operationen
---
>Sets sind wie immer Unique Values
```python
# Elemente (Items) zu einem Set hinzufügen  
redis_client.sadd('mein_set', 'item1', 'item2', 'item3')  
# Prüfen, ob ein spezielles Element im Set ist  
redis_client.sismember('mein_set', 'item2') # True  
# Alle Elemente eines Sets auslesen  
members = redis_client.smembers('mein_set') 
# Anzahl der Elemente
redis_client.scard('mein_set') # 3
# Ausgabe der Elemente  
print([member.decode('utf-8') for member in members])
```
# Sorted Set Operationen
---
```python
# Spieler mit den erzielten Punkten in ein sortiertes Set schreiben  
redis_client.zadd('leaderboard', {'spieler1': 100, 'spieler2': 200,  
'spieler3': 150})  
# Die Position (rank) eines Spielers auslesen  
redis_client.zrank('leaderboard', 'player2')   # Ausgabe: 2  
# Die Top-Spieler ermitteln  
top_players = redis_client.zrange('leaderboard', 0, 2, desc=True,  
withscores=True)
# Das gesamte Set ausgeben
c.zrange("leaderboard", 0, -1)
#Ausgabe der Top-Spieler  
print([(player.decode('utf-8'), score) for player, score in top_players])
```
# Pipeline Operationen
---
```python
# Aufbau einer Redis-Pipeline  
with redis_client.pipeline() as pipe:  
	pipe.set('key1', 'value1')  
	pipe.set('key2', 'value2')  
	pipe.set('key3', 'value3')  
	pipe.execute()
```
# Error Handling
---
```python
from redis import Redis, RedisError  
redis_client = Redis(host='localhost', port=6379, db=0)  
try:  
	redis_client.ping()  
except RedisError as e:  
	print(f"Error connecting to Redis: {e}")  
finally:  
	redis_client.close()
```
# Pub/Sub
---
Das Publish/Subscribe-Messaging Paradigma von Redis ermöglicht die Echtzeitkommunikation zwischen  
verschiedenen Teilen einer Anwendung oder zwischen verschiedenen Anwendungen.  

So funktioniert Redis Pub/Sub  
1. Publisher: Senden Nachrichten an bestimmte Kanäle, ohne zu wissen, wer (wenn überhaupt) zuhört.  
2. Subscriber: Hören einen oder mehrere Kanäle ab und empfangen Nachrichten in Echtzeit.  
3. Kanäle: Dienen als Leitungen für Nachrichten und ermöglichen themen-basiertes Messaging.

```python
import redis
import threading
redis_client = redis.Redis(host='localhost', port=6379, db=0)
def publish_message():
	while True:
		message = input("Enter message to publish: ")
		redis_client.publish('my_channel', message)

def subscribe_to_messages():
	pubsub = redis_client.pubsub()
	pubsub.subscribe('my_channel')
	for message in pubsub.listen():
		if message['type'] == 'message':
			print(f"Received: {message['data'].decode('utf-8')}")

# Start des publisher and subscriber in eigenen Threads  
threading.Thread(target=publish_message).start()  
threading.Thread(target=subscribe_to_messages).start()
```

# Session Verwaltung
---
Redis ist aufgrund seiner Geschwindigkeit und der Möglichkeit, Ablaufzeiten für Daten festzulegen, eine  
ausgezeichnete Wahl für die Verwaltung von Benutzersitzungen in Webanwendungen.  

Die Vorteile der Session-Verwaltung sind:  
- Geschwindigkeit: Der Speicher im Arbeitsspeicher ermöglicht einen schnellen Abruf von Sitzungsdaten. 
- Skalierbarkeit: Redis kann eine große Anzahl gleichzeitiger Sitzungen verarbeiten.  
- Verfallszeit (Expiration-Time): Die integrierte Unterstützung für die Gültigkeit von Schlüsseln vereinfacht die Verwaltung von Zeitüberschreitungen.  
- Persistenz: Optionen zum Speichern von Sitzungsdaten auf der Festplatte, falls erforderlich

```python
from flask import Flask, session  
from redis import Redis  
import uuid

app = Flask(__name__)  
app.secret_key = 'your_secret_key'  
redis_client = Redis(host='localhost', port=6379, db=0)

@app.before_request  
def before_request():  
	session.permanent = True  
	app.permanent_session_lifetime = timedelta(minutes=30)  
	session.modified = True  
	session['redis_id'] = session.get('redis_id', str(uuid.uuid4()))

@app.route('/set_data')  
def set_data():  
	redis_client.hset(f"session:{session['redis_id']}", 'username',  
	'john_doe')  
	return 'Data set in Redis'

@app.route('/get_data')  
def get_data():  
	username = redis_client.hget(f"session:{session['redis_id']}", 'username')  
	return f'Username: {username.decode("utf-8") if username else "Not set"}'  

if __name__ == '__main__': 
	app.run(debug=True)
```