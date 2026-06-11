---
tags:
Fach: "[[BA]]"
Thema:
  - "[[Linux]]"
---
Aufruf von [[Console#VI|VI]] mit `vi <datei.txt>`

![[Pasted image 20241205151826.png]]

# q!
Beenden und nicht gespeichertes verwerfen
# wq
write quit
speichern und verlassen
# Cursor
Tasten `h`, `j`, `k`, `l`!
# Vom *command mode* in den *insert mode*
``esc i``
# In welchem Modus können Sie den Cursor bewegen?
Mit ``h j k l`` im *Command Mode*
# In welchem Modus können sie Texte löschen?
deletion (`commandmode` `x`)
# Eine Datei unter einem anderen Namen speichern
`:wq dateiname`
# Suchen
Im *Command mode* `/Suchbegriff`
- `n`: ein Treffer weiter
- `N`: ein Treffer zurück
# Zeile kopieren
`d`
# Zeile ausschneiden
`dd`
# Zeile einfügen
`p`
# Cursor in die erste Zeile
`gg`
# Cursor in die letzte Zeile
`G`
# Cursor ans Zeilenende
`$`
# Rückgängig machen
`u` oder `Ctrl+r`
# Datei leeren
`:e!`