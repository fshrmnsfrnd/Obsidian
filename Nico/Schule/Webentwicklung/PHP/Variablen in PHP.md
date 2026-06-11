---
Fach:
tags:
Thema:
  - "[[PHP]]"
  - "[[Webentwicklung]]"
---
# Variablendefinition
- Case Sensitive
- Alphanumerische Zeichen und Unterstrich
- werden mit $ am Anfang markiert

# Strings

Doppelte Anführungszeichen("):
```php
$a = 1;
$b = "\$a hat den Wert $a"; //Ohne Escape wird der Variablenwert ausgegeben
```

Einfache Anführungszeichen
```php
$a = 1;
$b = '$a'; //wird als String gelesen
```

Zwei Zeichenketten werden mit `.` vereinigt
```php
$a = "abc";
$b = "def";
$c = $a . $b; //"abcdef"
```

Etwas im String ändern
```php
str_replace(string $toReplace, string $replaceValue, $stringToOperate); 
//Return Type String
```

date('Y-m-d H:i')

# Datentypen umwandeln
Hierfür wird der gewünschte Datentyp in klammern vor die Variable geschrieben
```php
$str = "2";
$int = (int) $str;
```