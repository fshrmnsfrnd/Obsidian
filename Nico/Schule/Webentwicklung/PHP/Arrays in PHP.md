---
Thema:
  - "[[PHP]]"
  - "[[Webentwicklung]]"
---
## Arrays
Array erstellen
```php
$a1 = array();
//oder
$a1 = [];
```

Array initialisieren
```php
$a2 = [1, 2, 3];
```

Array ausgeben
```php
print var_dump($arr);
//oder
print_r($arr);
```

Elemente anhängen
```php
array_push($arr, "abc");
//oder
$arr[] = "abc";
$arr[15] = "def";
```

Länge ausgeben
```php
print sizeof($array);
```

Schleife
```php
foreach($array as $value){
	print $value;
}
```
# Assoziative Arrays

Array initialisieren
```php
$a2 = ["Name"=>"Maier", "Vorname"=>"Anton"];
```

Elemente anhängen
```php
$arr["Geburtsdatum"] = "12.03.2001";
```

Array ausgeben
```php
print var_dump($arr);
//oder
print_r($arr);
```

Länge ausgeben
```php
print sizeof($array);
```

Schleife
```php
foreach($array as $key => $value){
	print $key;
	print $value;
}
```

Ausgeben
```php
var_dump($array);
```