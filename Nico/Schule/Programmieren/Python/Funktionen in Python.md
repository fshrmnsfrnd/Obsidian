---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[Python]]"
---
# Funktionen definieren
```python
def <Funktionsname>(Param1, Param2):
	print("Programm")
	return <Value>
```
## Funktion aufrufen
```python
<Variable> = <Funktionsname>(<Param1>, ...) 
```
# Funktionen mit mehreren Rückgabewerten definieren
```python
def <Funktionsname>(Param1,Param2,….):
	print("Programm")
	return <Returnvalue1>, <Returnvalue2>, ...
    
```
## Aufruf
```python
<VariableResult1>, <VariableResult2>, …= (<Value Param1>, <Value Param2>, …..)
```

# Optionale Parameter
Bei der Definition einer Funktion können am ende **Optionale Parameter** bzw. Parameter mit **default** Wert definiert werden. Diese müssen beim Aufruf nicht zwingend angegeben werden:  

```python
def addieren(zahl1, zahl2, zahl3=0, zahl4=0 ):
	print("Zahl1 = ",zahl1,"Zahl2 =",zahl2,"Zahl3 =",zahl3,"Zahl4 =",zahl4)
	return zahl1+zahl2+zahl3+zahl4

print ("2+4 =",addieren(2,4)) #Ausgabe : 2+4 = 6
print ("2+4+5 =",addieren(2,4,5)) #Ausgabe : 2+4+5 = 11
print ("2+4+5+6=",addieren(2,4,5,6)) #Ausgabe : 2+4+5+6= 17
``` 

# Schlüsselwort Parameter
Ein sehr nützliches Feature wenn man nicht weiß in welcher Reihenfolge die Parameter angegeben werden müssen kann man diese über das **Schlüsselwort** in beliebiger Reihenfolge angeben:  
```python
ergebnis = addieren(zahl1=4,zahl2=5,zahl4=6)
#Ausgabe in Funkton : Zahl1 = 4 Zahl2 = 5 Zahl3 = 0 Zahl4 = 6
print ("4+5+6=",ergebnis) #Ausgabe : 4+5+6= 15
```

# Beliebig viele Parameter
Es kann auch über `*` definiert werden das man eine beliebige Anzahl an Parameter übergeben kann:  
```python
def vieleParameter(eins, *derRest):
	print("1 ter Parameter",eins)
    i=2
    # derRest wird als Tupel behandelt
    for param in derRest:
    print(i," ter Parameter",param)
    i=i+1
          
vieleParameter("Test","zwei",3,4,5,6)
vieleParameter("Test","zwei",3,4,5,"sechs","sieben")
```

# Typisierung

Wie oben schon erwähnt gibt es in Python keine Type-Checks. Jedoch kann man sich in der IDE die gewünschten Typen anzeigen lassen. Dafür muss der Entwickler aber die Parameter und Return-Werte **typisieren**.  

```python
def funktion1(param1: <datentyp1>, param2: <datentyp2>, ...) -> <rückgabe datentyp>:
```
Hier ein Beispiel:  
```python
def addieren(zahl1: float, zahl2: float) -> float:
	return zahl1 + zahl2

def concat(str1: str, str2: str) -> str:
  return f'{str1} {str2}'
```