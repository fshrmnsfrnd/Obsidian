---
Thema:
  - "[[Python]]"
---
# while-Schleife
Die **Kopfgesteuerte Schleifen**: Werden durch eine Bedingung am **Anfang** der Schleife (im Kopf der Schleife) kontrolliert, dadurch hat man eine Überprüfung bevor die Schleife das erste mal gestartet wird werden in Python so geschrieben:  
```python    
i = 0
while i < 7:
	print(i)
	i++
else:
	print("Schleife ist fertig!")
```
Es gibt **KEINE** **Fußgesteuerte Schleife**: Werden durch Bedingungen am **Ende** der Schleife (im Fuß der Schleife) kontrolliert, hier ist ein einmaliger Durchlauf der Schleife garantiert!  

## for-Schleife
In Python gibt es auch **Zählergesteuerte Schleife**: Hier wir die Schleife eine bestimmte Anzahl durchlaufen.:  
```python
for x in [2,3,4]:
	print(x)

# Definition einer Range bis 99 (Die angegebene Zahl ist ausgeschlossen)
for i in range(100):
	print(i)
  
# Zahlen von 5 bis 15
for i in range(5,15)
	print(i)
    
# Zahlen von 5 bis 950 in 50er Schritten
for i in range(0,1000,50)
	print(i)
```

