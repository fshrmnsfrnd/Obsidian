---
Thema:
  - "[[PHP]]"
  - "[[Webentwicklung]]"
---
>Cookies sind Key-Value Daten, die vom Browser gespeichert werden und von anderen Skripten wieder verwendet werden können. Beim Setzen der Cookies wird festgelegt, wie lange die Daten gültig sind.

Cookies können einfach in Browser über die Developer Tools einfach geändert werden, daher sind sie nicht sicher. Bei kritischen Daten Cookies nur verschlüsselt speichern.

# Erstellen
```php
setcookie($key,$value,$ablaufzeit);
```
Ablauf: `Time() + 3600*24*3` 1 Stunde * 1 Tag * 3 = 3 Tage in Sekunden umgewandelt
# Lesen
```php
$_COOKIE[$key];
```
