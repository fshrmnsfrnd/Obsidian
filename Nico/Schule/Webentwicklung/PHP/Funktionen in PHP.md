---
Thema:
  - "[[PHP]]"
  - "[[Webentwicklung]]"
---
# Definieren
```php
function funcName($param1, $param2=2){
	return $param1 / $param2;
}
```
`$param2` hat hier einen Default Wert und ist somit optional.
# Aufrufen
```php
funcName($wert);
```

# Unbestimmte Anzahl an Parametern
```php
function funcName2(...$werte){
	foreach($werte as $wert){
		//Zugriff
	}
}

funcName2(1, 2, 5, 2, 10);
```
