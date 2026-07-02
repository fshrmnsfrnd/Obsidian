---
Thema:
  - "[[PHP]]"
  - "[[Webentwicklung]]"
---
**Beim Aufruf eines PHP-Programms werden die folgenden Schritte ausgeführt: 
1. Der Webbrowser (Client) fordert das Dokument beim Webserver an. 
2. Der Webserver erkennt an der Endung des Dateinamens (z.B. `.php`), dass es sich um ein PHP-Skript handelt und startet den entsprechenden Interpreter für das Programm. Das Programm wird auf dem Server ausgeführt.
3. Die vom Programm erzeugten Ausgaben (meist HTML-Format) werden an den Webbrowser, der das Dokument aufgerufen hat, zurückgesendet. 
4. Der Browser zeigt die Ausgaben an.

# PHP Code einbinden
In einer `.php` Datei: 
Beginn von PHP Block : `<?php`
Ende von PHP Block: `?>`
Je nach Webserver ist auch `<? ?>` möglich

Error logs sind per Default aus, sie können eingeschalten werden indem im Dokument `error_reporting(E_ALL);` oben eingefügt wird.

# Operatoren

| Rechenoperation           | Mathematische Schreibweise                                                 | PHP-Schreibweise |
| ------------------------- | -------------------------------------------------------------------------- | ---------------- |
| Addition                  | a+b                                                                        | $a + $b          |
| Subtraktion               | a-b                                                                        | $a - $b          |
| Multiplikation            | a * b                                                                      | $a * $b          |
| Division                  | a:b                                                                        | $a / $b          |
| Rest der Ganzzahldivision | a modulo b                                                                 | $a % $b          |
| Exponent                  | a$^b$                                                                      | $a ** $b         |
| ++$x                      | x wird um den Wert 1 erhöht, bevor x im Ausdruck weiter verwendet wird.    |                  |
| --$x                      | x wird um den Wert 1 erniedrigt, bevor x im Ausdruck weiter verwendet wird |                  |
| $x++                      | x wird inkrementiert, nachdem x im Ausdruck verwendet wurde                |                  |
| $x--                      | x wird dekrementiert, nachdem es im Ausdruck verwendet wurde               |                  |
# Vergleichsoperatoren

| Vergleich                                                                    | PHP-Schreibweise |
| ---------------------------------------------------------------------------- | ---------------- |
| a gleich b                                                                   | $a ==$b          |
| a größer b                                                                   | $a > $b          |
| a kleiner b                                                                  | $a < $b          |
| a größer oder gleich b                                                       | $a >= $b         |
| a kleiner oder gleich b                                                      | $a <= $b         |
| a ungleich b                                                                 | $a != $b         |
| a gleich b und der Typ von a ist gleich dem Typ von b (strings `==`)         | $a `===`$b       |
| a ungleich b oder der Typ von a ist nicht gleich dem Typ von b (strenges !=) | $a !== $b        |
# Bitoperationen

| Beispiel | Name                    | Ergebnis                                                                                                      |
| -------- | ----------------------- | ------------------------------------------------------------------------------------------------------------- |
| $a & $b  | Und                     | Bitweise Und-Verknüpfung                                                                                      |
| $a \| $b | Oder                    | Bitweise Oder-Verknüpfung                                                                                     |
| $a ^ $b  | Xor                     | Bitweise XOR-Verknüpfung                                                                                      |
| ~$a      | Nicht                   | Bitweises invertieren                                                                                         |
| $a << $b | Nach links verschieben  | Verschiebung der Bits von $a um $b Stellen nach links (Jede Stelle entspricht einer Multiplikation mit zwei). |
| $a >> $b | Nach rechts verschieben | Verschiebt die Bits von $a um $b Stellen nach rechts (jede Stelle entspricht einer Division durch zwei).      |
# Verzweigung

## IF
```php
if ($true){ 
//Code
}elseif($true){ 
//Code
}else{ 
//Code
}
```

## Switch Case
```php
switch(Ausdruck){ 
case Konstante: Anweisung; 
case Konstante : Anweisung; 
default : Anweisung; 
}
```

# Schleifen
## while Schleife
```php
while ($true){
//Code
}
```

## do-while Schleife
```php
do{
//code
}while($true);
```

## for Schleife
```php
for ($i = 0; $i < 2; $i++){
//code
}
```

## foreach Schleife
```php
foreach($array as $value){
	print $value;
}
```

```php
foreach($array as $key => $value){
	print $key;
	print $value;
}
```