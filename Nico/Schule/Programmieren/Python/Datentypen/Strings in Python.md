---
Fach: "[[Programmieren]]"
tags:
Thema:
  - "[[Python]]"
---
>Ein String ist einer Liste sehr ähnlich. Es ist eine Kette von Zeichen, welche alle als eigene Objekte der Liste verwendet werden können.
# Verketten
```python
str1 = "abc"
str2 = "def"
str3 = str1 + str2 #"abcdef"
```

# Zugriff über Index
```python
str1 = "abc"
str1[1] #Rückgabe: "b"
```

# Zugriff über For Schleife
```python
for letter in str1:
	print(letter)
```
Hier werden die Zeichen nacheinander durchgegangen.

# String umdrehen
```python
reverseStr1 = str1[::-1]
```

# Formatieren von Strings
Zum Formatieren von Ausgaben verwendet man einen Formatstring mit Platzhaltern für variable Werte. Die Platzhalter bestehen aus geschweiften Klammern in denen ggf. Formatierungsanweisungen enthalten sind. Die Methode Format ersetzt die Platzhalter mit den übergebenen Werten in der angegebenen Reihenfolge.
```python
formatstring = "Zahl1 : {} , Zahl2 : {}" 
print (formatstring.format(123,345)) 
# Ausgabe: Zahl1 : 123 , Zahl2 : 345
```
Die Reihenfolge kann auch geändert werden über ids der Platzhalter
```python
formatstring = "Zahl1 : {a} , Zahl2 : {b} , Zahl3 : {c} , Zahl4 : {d}" 
print (formatstring.format(b=7,a=3,c=0,d=1)) 
# Ausgabe: Zahl1 : 3 , Zahl2 : 7 , Zahl3 : 0 , Zahl4 : 1
```

## Formatierungsanweisungen
Nach dem Namen des Platzhalters kann noch eine Formatierungsanweisung eingefügt werden. Sie wird durch einen Doppelpunkt vom Namen des Platzhalters getrennt. Eine einfache Zahl gibt an, wie viele Zeichen die Ausgabe des Wertes einnehmen soll.
```python
formatstring = "{:*^4}|{:*^4}" 
for i in range(5): 
	print(formatstring.format(i,i**2)) 
	#Ausgabe: 
	#*0**|*0** 
	#*1**|*1** 
	#*2**|*4** 
	#*3**|*9** 
	#*4**|*16*
```
# String Methoden

| Methode                               | Beschreibung                                                                                            | Beispiel                                     |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------- | -------------------------------------------- |
| `len()`                               | Gibt die Länge eines Strings zurück                                                                     | `len("hello") #Rückgabe: 5`                  |
| `split(<trennzeichen>)`               | Splittet einen String am Trennzeichen und gibt Liste zurück                                             | `"ab".split("") #Rückgabe ["a", "b"]`        |
| `splitlines()`                        | Splittet einen String am Zeilenumbruch und gibt Liste zurück                                            | `"a\nb".splitlines("") #Rückgabe ["a", "b"]` |
| `find(<string>)`                      | Sucht den string im string und gibt den Index zurück. Nicht gefunden = -1                               | `"abcd".find("bc") #Rückgabe 1`              |
| `replace(<toReplace>, <replaceWith>)` | Ersetzt den ersten Substring mit dem zweiten. Wird der String öfter gefunden wird er jedes mal ersetzt. | `"abc".replace("b", "d") #Rückgabe "adc"`    |
| `upper()`                             | Macht alle Buchstaben zu Großbuchstaben                                                                 | `"abC".upper() #Rückgabe "ABC"`              |
| `lower()`                             | Macht alle Buchstaben zu Kleinbuchstaben                                                                | `"ABc".lower() #Rückgabe "abc"`              |
| `strip()`                             | Entfernt alle Unsichtbaren Zeichen an Anfang und Ende (z.B. \n, Leerzeichen)                            | `"\n abc  ".strip() #Rückgabe "abc"`         |
| `format()`                            | [[Schule/Programmieren/Python/Datentypen/Datentypen#Formatieren von Strings\|Formatieren von Strings]]             |                                              |
| `isalpha()`                           | Überprüft ob der String aus Buchstaben besteht. Gibt `True` oder `False` zurück                         |                                              |
| `isalnum()`                           | Überprüft ob der String aus Buchstaben und Zahlen besteht. Gibt `True` oder `False` zurück              |                                              |
| `isdigit()`                           | Überprüft ob der String aus Zahlen besteht. Gibt `True` oder `False` zurück                             |                                              |
| `islower()`                           | Überprüft ob der String aus Kleinbuchstaben besteht. Gibt `True` oder `False` zurück                    |                                              |
| `isupper()`                           | Überprüft ob der String aus Großbuchstaben besteht. Gibt `True` oder `False` zurück                     |                                              |
