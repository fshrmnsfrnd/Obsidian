---
Thema:
  - "[[Databases]]"
  - "[[NoSQL]]"
---
Redis bedeutet: Remote Dictionary Server. Redis ist ein open-source In-Memory-Datenspeicher, der als  
Datenbank, Cache, Message Broker und Warteschlange verwendet werden kann. Er ist bekannt für seine  
außergewöhnliche Leistung, Vielseitigkeit und Einfachheit, was ihn zu einer beliebten Wahl für verschiedene  
Anwendungen macht, die einen schnellen Datenzugriff und eine schnelle Datenbearbeitung erfordern.  

Einige Key-Features 
**In Memory**: Redis speichert Daten in erster Linie im Arbeitsspeicher. Dadurch sind Lese- und Schreibvorgänge extrem schnell. Deshalb eignet es sich ideal für Anwendungsfälle, die einen Datenzugriff mit geringer Latenz erfordern.  
**Persistenz**: Redis ist zwar eine In-Memory-Datenbank, bietet aber auch Optionen für die Persistenz von Daten auf der Festplatte, wodurch die Datenbeständigkeit bei Systemausfällen oder Neustarts gewährleistet ist.  
**[[Knowledge Base/Databases/NoSQL/Redis/Datenstrukturen|Datenstrukturen]]**: Redis unterstützt verschiedene Datenstrukturen: Strings, Hashes, Listen, Sets, sortierte Sets, Bitmaps, Hyperloglogs und Geodatenindizes.  
**Atomare Operationen**: Redis bietet atomare Operationen für diese Datentypen, wodurch komplexe Manipulationen ohne externe Sperrmechanismen möglich sind.  
**Pub/Sub-Messaging**: Redis umfasst ein Publish/Subscribe-Messaging-Paradigma, das für die Erstellung von Echtzeitanwendungen und die Implementierung der Kommunikation zwischen verschiedenen Teilen eines Systems nützlich ist.  
**Transaktionen**: Redis unterstützt Transaktionen, sodass Sie mehrere Befehle als eine einzige atomare Operation ausführen können.  
**Lua-Skripting**: Redis verfügt über integrierte Lua-Skripting-Funktionen, mit denen Sie komplexe Operationen schreiben können, die direkt auf dem Redis-Server ausgeführt werden.  
**Replikation**: Redis unterstützt Master-Slave-Replikation, die zur Verbesserung der Leseskalierbarkeit und zur Erstellung von Hot-Backups verwendet werden kann.  
**Cluster-Modus**: Redis Cluster bietet eine Möglichkeit, eine Redis-Installation auszuführen, bei der Daten  
automatisch auf mehrere Redis-Knoten verteilt werden.
