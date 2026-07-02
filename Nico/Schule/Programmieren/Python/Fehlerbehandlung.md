---
Thema:
  - "[[Python]]"
---
Um Fehler abzufangen gibt es in Python die **try - except** Blöcke. Diese haben folgende Teile:  
- `try`: Der Code der einen Fehler werfen könnte wird hier ausgeführt  
- `except`: Hier kommt der Code welcher die Fehler abfängt (z. B. Fehlermeldung erzeugen)  
- `else`: Wenn der `try` Block erfolgreich durchgelaufen ist wird dieser Code ebenfalls ausgeführt  
-  `final`: Wird **immer** nach dem try - except ausgeführt, egal ob ein Fehler aufgetreten ist oder nicht  
Dabei ist **else** und **final** nicht zwingen nötig.  

```python
try:
    datei = open("Datei.txt","r")
except:
    print ("Fehler!")
else:
    for zeile in datei:
        print (zeile)
    datei.close()
```

In Python können Fehlerklassen spezifiziert werden. Die verschiedenen Klassen findet man [hier](https://docs.python.org/3/library/exceptions.html)
```python  
try:
	datei = open("Datei.txt","r")
except FileNotFoundError:
    print ("Datei ist nicht vorhanden")
except PermissionError as e:
	print ("Datei darf nicht gelesen werden")
    print (e)
except:
    print ("Sonstiger unbekannter Fehler")
else:
	for zeile in datei:
		print (zeile)
	datei.close()
finally:
	print("Fertig, egal was passiert ist.")
```

