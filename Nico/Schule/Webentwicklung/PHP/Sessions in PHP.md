---
tags:
Fach:
Thema:
  - "[[PHP]]"
  - "[[Webentwicklung]]"
---
Sessions ermöglichen das Speichern von Daten auf dem Server, die dann jeweils einer bestimmten `SessionID` zugeordnet sind. PHP-Skripten, die die Session mit dieser ID fortsetzen, können auf die gespeicherten Daten zugreifen. 

Startet ein Skript eine Session ( `session_start()` )wird überprüft, ob schon eine `SessionID` vorhanden ist. Wenn noch keine `SessionID` vorhanden ist, wird eine `SessionID` erstellt und den Browser als `COOKIE` geschickt und dort gespeichert. 

Ist die `SessionID` vorhanden (als Cookiewert vom Browser mitgeschickt), werden mit dem Start der Session automatisch alle zu dieser `SessionId` gespeicherten Daten in das assoziative Array `$_SESSION` (Systemvariable) geladen. Nachdem eine Session gestartet wurde, kann das Array `$_SESSION` verändert und erweitert werden. Am Ende des PHP-Skripts werden die Daten im Array `$_SESSION` automatisch abgespeichert.

```php
// Erstes Skript 
session_start(); 
$_SESSION['gruss']='Hallo Hallo'; 
// Zweites Skript 
session_start(); 
print $_SESSION['gruss'];
```
