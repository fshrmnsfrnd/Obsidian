---
Thema:
  - "[[Redis]]"
---
Redis unterstützt mehrere logische Datenbanken innerhalb einer einzigen Instanz. Standardmäßig gibt es 16 Datenbanken, nummeriert von 0 bis 15. Mit dem Befehl MOVE können Sie einen Schlüssel von der aktuell ausgewählten Datenbank in eine andere übertragen. Standardmäßig sind Sie mit der Datenbank 0 verbunden.

# Key bewegen
```cli
127.0.0.1:6379> SET Inventar:1:titel "W50123456"  
OK 
127.0.0.1:6379> MOVE Inventar:1:titel 1  
(integer) 1
```

# Datenbank wählen
```cli
127.0.0.1:6379> SELECT 1  
OK  
127.0.0.1:6379> GET Inventar:1:titel  
"W50123456"
```