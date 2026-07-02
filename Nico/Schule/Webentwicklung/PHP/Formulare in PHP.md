---
Thema:
  - "[[PHP]]"
  - "[[Webentwicklung]]"
---
# Formularattribute
```html
<form action="formularAuswertung.php" method="POST" enctype="multipart/form-data">
```
**Action:** Welches PHP Skript soll aufgerufen werden, wenn der Submit Button geklickt wird
**Method:** Welche Übertragungsmethode verwendet werden soll (`GET` oder `POST`)
**Enctype:** Wie die Daten verschlüsselt werden sollen

>Ein Formular muss mindestens ein Interaktives Element mit dem `type="submit"` haben

## POST
- POST Daten sind im HTTP-Request enthalten und deshalb nicht so offensichtlich. Die Daten werden aber trotzdem unverschlüsselt übertragen (HTTP), wenn die Verbindung nicht insgesamt gesichert ist (HTTPS) 
- POST hat keine Beschränkung für die Datenmenge, die übergeben werden soll 
- Formulareingaben können nicht in Lesezeichen gespeichert werden.

## GET
- Die Daten werden an die URL angehängt 
- Die Länge der URL ist begrenzt. Umfangreiche Daten können so nicht übertragen werden.
- Sensible Daten sollten nicht mit GET übertragen werden. Die URL eines Aufrufs und damit die übertragenen Daten sind leicht sichtbar und manipulierbar. 
- GET ist sehr sinnvoll, wenn die genaue Anfrage incl. übergebene Daten in einem Lesezeichen gespeichert werden soll.
### Syntax in der URL:
`URL?variablenName=1&VariableZwei=abc`

# Felder im Formular
Ein Formular muss mindestens ein Interaktives Element mit dem `type="submit"` haben
`<input type="submit" value="Senden">`

Auf die Werte der Felder im Formular kann über den `Key` in ihrem `name` Tag zugegriffen werden. z.B.:
```php
//html
<form action="./script.php" method="GET">
    <label>Suchbegriff <input name="search"></label>
    <button type="submit">finden</button>
</form>

//php script.php
print $_GET['search'];
```

# Auswertung
Die Daten sind in dem Aufgerufenen Skript zugänglich über
`$_POST['name']`
oder
`$_GET['name']`
Je nachdem, welche Methode gewählt wurde