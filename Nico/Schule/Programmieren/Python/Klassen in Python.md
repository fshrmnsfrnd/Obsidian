---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[Python]]"
---
# Definition
---
``` python
class <ClassName>:
    def __init__(self[, Params]) -> <ReturnType>:
        #Konstruktor

    def <methodName>(self[, Params]) -> <ReturnType>:
        #Methoden Code
```

Bei allen Methoden wird als erste Parameter **IMMER** `self` übergeben. 
Attribute und Methoden können ebenfalls über `self.<attributname>` bzw. `self.<methodenname>` aufgerufen werden.  

> [!NOTE] Mehrere Konstruktoren sind in Python nicht möglich
# Sichtbarkeit
---
Es gibt **KEINE** Kapselung in Python im Gegensatz zu Java. Wenn man eine Variable `private` machen möchte dann benennt man sie mit `_` am Anfang. Sie ist nicht wirklich `private` aber andere Entwickler erkennen, dass diese nicht manuell geändert werden darf.  
# Properties
---
Man kann in Python sogenannte **Properties** (Eigenschaften) von Klassen definierten. Diese werden dann z. B. auch in der IDE beim erstellen eins Objektes angezeigt:  
```python
class <ClassName>:
    <attributName>[ = <value>]
    
    def <getMethod>(self) -> <typeOfVariable>:
        return <variable>

    def <setMethod>(self, <param>) [-> [None|<typeOfVariable]]:
        self.<attributName> = <param>

    <propertyName> = property(<getMethod>,<setMethod>)
```
Verwenden der Property:
```python
<objectName> = <ClassName>()
print(<objectName>.<propertyName>)
<objectName>.<propertyName> = <value>
```
# Vererbung
---
```python    
class <superClassName>:
    def __init__(self, <param1>) -> None:
        self.<attribut1> = <param1>

class <ClassName>(<superClassName>):
    def __init__(self, <param1>, <param2>) -> None:
        super().__init__(<param1>)
        self.<attribut2> = <param2>
```
