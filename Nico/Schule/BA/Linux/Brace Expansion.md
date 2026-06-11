---
tags:
Fach: "[[BA]]"
---
# {}

>==Für jedes== Zeichen in dieser Klammer

Beispiel:
`a{b,c,d}` gibt 
`ab ac ad` zurück.

>kann auch kombiniert werden:

`{a,b}{1,2}` gibt dann 
`a1 a2 b1 b2` aus.

>oder ineinander

`{a,b{c,d}}e` erzeugt
`ae bce bde`
# Dateien/Verzeichnisse erzeugen

Mit [[Console#touch|touch]] können nun damit mehrere Dateien erzeugt werden.

`touch <pfad>/{a,b}.txt` erzeugt:
`<pfad>/a.txt <pfad>/b.txt`

