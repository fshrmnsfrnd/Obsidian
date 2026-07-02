---
Thema:
  - "[[PHP]]"
  - "[[Webentwicklung]]"
---
# Gesamte Datei lesen
## Einlesen
```php
file_get_contents ( string $filename ) //Return Type String
```

# Datei zeilenweise verwenden
## Öffnen
```php
fopen ( string $filename , string $mode ) //Return Type resource bzw Stream
```
`$filename` : ./Pfad/zur/Datei
`$mode`: 
	`r` : lesen
	`w`: schreiben
	`a`: anhängen

## Lesen
```php
fgets ( resource $handle ) //Return Type: String
```
Liest ab dem aktuellen Dateizeiger ($handle) eine Zeile aus der Datei und gibt den Text als Funktionswert zurück. Im Fehlerfall (z.B. Dateiende) wird false zurück geliefert.

### Beispiel
```php
$csv = fopen("Messwerte.csv", "r");
print '<table>';
while ($zeile = fgets($csv)) {
    $line = explode(",", $zeile);
    print '<tr>';
    foreach ($line as $value) {
        print "<td>$value</td>";
    }
    print "</tr>";
}
print "</table>";
fclose($csv);
```

## Schreiben
```php
fputs ( resource $handle , string $string ) // Return Type int
```
Schreibt ab dem aktuellen Dateizeiger ($handle) eine Zeile in die Datei. Im Fehlerfall (z.B. Dateiende) wird false zurück geliefert ansonsten die Anzahl der geschriebenen Bytes. 
Achtung! Das Zeilenende-Zeichen wird nicht automatisch eingefügt!

### Beispiel
```php
$csv = fopen("Messwerte.csv", "a");
        $werte = $_GET['temperatur'] . ",";
        $werte .= $_GET['wetterbeschreibung'] . ",";
        $werte .= $_GET['messzeit'] . "\n";
        print $werte;
        fputs($csv, $werte);
        fclose($csv);
```

## Schließen
```php
fclose ( resource $handle )
```

## Beispiel
```php
// Datei öffnen 
$dateiname = "dateien/datei1.txt"; 
if (!$dateizeiger = fopen($dateiname, "r")) { //Fehlerbehandlung
	print "Kann datei $dateiname nicht öffnen!"; 
	exit; 
} 
// Datei zeilenweise lesen und ausgeben 
while ($zeile = fgets($dateizeiger)) { 
	print("$zeile"); 
} 
fclose($dateizeiger);
```

# In Datei schreiben
```php
file_put_contents ( string $filename ,mixed $data )
```
Die übergebenen Daten (meist ein String) werden in die Datei mit dem übergebenen `$filename` (rel. Pfad + Dateiname) geschrieben. Die zuvor enthaltenen Daten werden überschrieben.


# CSV Dateien
Wie [[Dateien in PHP#Datei zeilenweise verwenden]]
```php
explode ( string $delimiter , string $string ) //Return Type Array
```
Liefert ein Array aus Strings zurück. Der übergebene string wird in Teile geteilt. Das Trennzeichen wird in `$delimiter` übergeben.

```php
implode ( string $glue , array $pieces ) //Return Type Array
```
Fügt alle Teile eines Arrays in einem String zusammen. Die einzelnen Teile werden durch das Zeichen `$glue` getrennt.