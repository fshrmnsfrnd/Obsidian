---
Thema:
  - "[[Python]]"
---
>Tupel können ähnlich verwendet werden wie [[Listen]].  Allerdings sind sie dafür gedacht, nicht verändert zu werden.

```python
tupel1 = (1, 2, 3, 4)
tupel2 = ("apfel", ) # Tupel mit nur einem Element braucht ein Komma

# Tupel in Liste umwandeln
liste1 = list(tupel1)
   
# Auf Tupel zugreifen
print(tupel1[2]) # Ausgabe: 3
```