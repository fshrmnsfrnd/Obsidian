---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[Python]]"
---
# Library importieren
```python
import matplotlib.pyplot as plt
```

# Graph erstellen
```python
xListe = [1, 2, 3, 4]
yListe = [1, 2, 3, 4]

plt.plot(xListe, yListe, color="g", label="Line1") #g = green r = red usw.
[plt.plot(x, y)] # Ein zweiter Graph, der im selben Koordinatensystem angezeigt wird
plt.legend() # Show Legend for linecolors and labels
plt.grid() # Shows lines at marked Values
plt.show()
```

## Subplot
Mehrere Graphen in verschiedenen Koordinatensystemen in einem Grid anzeigen.
`subplot(<rows>, <cols>, <position>)`
**Beispiel:**
```python
#2*2 Raster
plt.subplot(2,2,1) #Oben links
plt.plot(xListe,y1)

plt.subplot(2,2,2) # Open rechts
plt.plot(xListe,y2)

plt.subplot(2,2,3) #Unten links
plt.plot(xListe,y3)

plt.subplot(2,2,4) #Unten Rechts
plt.plot(xListe,y4)
```


# Scatter (Punkte im Koordinatensystem)
```python
plt.scatter(xListe, yListe)
plt.show
```

# Histogram (Säulendiagramm)
```python
plt.hist(yListe)
```