---
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
# Einbinden
Momentan muss in den HTML-Dokumenten, die dynamisch an die Fenster Größe angepasst werden sollen noch der Metatag [[Viewport]] gesetzt werden:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Mit Hilfe des media-Attributs kann im link-Tag angegeben werden für welchen Medientyp und welche Medienmerkmale das Stylesheet eingebunden werden soll. 
**Beispiel:**
```html
<head>
	<link rel="stylesheet" href="bildschirm-stylesheet.css" media="screen">
	<link rel="stylesheet" href="druck-stylesheet.css" media="print">
	<link rel="stylesheet" href="kompakt.css" media="(orientation: portrait)">
</head>
```

# Abfragen
```css
@media screen and (max-width:1000px) { 
	div { 
		color: white; 
	} 
}

@media (width<800px){
}

@media orientation:portrait{
}
```