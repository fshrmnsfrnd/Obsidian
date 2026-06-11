---
tags:
Fach:
Thema:
  - "[[HTML]]"
  - "[[Webentwicklung]]"
---
# Syntax

`<a href="link">Link</a>` 

# Linktypen

## Externe Links
Bei Zielen auf einer anderen Website.
`<a href="https://google.de/search">Google</a>` 

Der Link muss als vollständige URI angegeben werden.
Wird kein Protokoll angegeben wird das selbe verwendet, das gerade für die Website verwendet wird.
## Interne Links
`<a href="directory/datei.html">Datei</a>` 

# Relative Pfade

## Selbes Verzeichnis
`<a href="seite2.html">Seite2</a>` 
oder
`<a href="./seite2">Seite2</a>` 
## Unterverzeichnis
`<a href="seite2/index.html">Seite2</a>` 
oder
`<a href="./seite2/index.html">Seite2</a>` 

## Übergeordnetes Verzeichnis
Ein Verzeichnis nach oben = . . /
Zwei Verzeichnisse nach oben = . . / . . /
`<a href="../seite2.html">Seite2</a>` 
Um anschließend in einen anderen Unterordner zuzugreifen:
`<a href="../../seite2/index.html">Seite2</a>`  

# Sprungmarken
## zu Tags
Kann verwendet werden um auf der aktuellen Seite zu einem Tag mit der entsprechenden ID zu springen.
`<a href="#secondHeading">Nächste Überschrift</a>`
`<h1 id="secondheading">Überschrift</h1>`

## zum Seitenanfang
`<a href="#">Seitenanfang</a>` 
oder
`<a href="#top">Seitenanfang</a>` 

## Seite neu laden
Das geht mit einem leeren Link.
`<a href="">Neuladen</a>` 

