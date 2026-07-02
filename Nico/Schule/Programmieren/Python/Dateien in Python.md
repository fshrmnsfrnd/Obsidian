---
Thema:
  - "[[Python]]"
---
Um in Python auf Dateien im Dateisystem zugreifen zu können benötigt man die Funktion `open()` Dabei kann der Modus einer der drei Möglichkeiten sein:  
- `r`: read
- `w`: write (Vorhandene Datei wird überschrieben)  
- `a`: append (Vorhandene Datei wird erweitert)  

Am ende muss dann noch der **Stream** zu der Datei mit der Funktion `close()` geschlossen werden.  

# Datei finden
Wenn man eine Datei relativ zu dem aktuell ausgeführten Pyhton-Script aufrufen möchte muss man dies wie folgt tun:  
```python   
import os 
# Wenn der Code in einem normalen Python-Programm ausgeführt wird.
if ("__file__" in vars()):
	path, filename = os.path.split(os.path.abspath(__file__))
	dateiname = os.path.join(path,"textdatei1.txt")
else: # Beim Jupyter-Notebook ist der Dateiname ausreichend
	dateiname = ("textdatei.txt")
```
# Datei schreiben
```python
try:
	datei = open(dateiname,"w")
    for i in range(10):
    	j = i**2
    	datei.write(f"{i};{j}\n")
    datei.close()
except Exception as e: 
    print (f"Fehler beim Schreiben der Datei {dateiname}")
    #Fehlermeldung vom Interpreter ausgeben
    print(e)
	if datei:
    datei.close()
```

# Datei lesen
```python
try:
	datei = open(dateiname,"r")
    # Zeile für Zeile
    for zeile in datei:
	    # Zeile in Spalten teilen
	    spalten = zeile.strip().split(";")
	    print(f"{spalten[0]:4}|{spalten[1]:8}")
    	      
	    # Ganze Datei auf einmal
    	text = datei.read()
    	print("text = \n"+text)
    	      
	    # Liste mit Zeilen
    	zeilen  = datei.readlines()
    	print(zeilen)
    	      
    datei.close()
except Exception as e: 
    print (f"Fehler beim Lesen der Datei {dateiname}")
    print(e)
    if datei:
	    datei.close()
```

# Lesen/Schreiben mit `with`
Oft will man die Datei nur für einen Block geöffnet haben, dabei hilft die `with` Funktion:  
```python    
import os

path, filename = os.path.split(os.path.abspath(__file__))
dateiname = os.path.join(path,"textdatei1.txt")

try:
    with open(dateiname,"w") as datei:
        for zeile in datei:
            spalten = zeile.strip().split(";"))

except Exception as e:
    print (f"Fehler beim Schreiben der Datei {dateiname}")
    print(e)
```

