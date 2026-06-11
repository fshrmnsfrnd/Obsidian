---
Fach:
tags:
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
# Definieren
Mit Hilfe des Pseudoselektors `:root` können Sie Variablen definieren, die für die gesamte Website gültig sind.
```css
:root { 
	--hintergrund1: #ffffff; 
	--hintergrund2: #dddddd; 
	--schriftFarbe: #444488; 
	--schriftFarbe2: #000088; 
	--radius: 0.5em; 
}
```

# Verwenden
```css
body { 
	--schriftFarbe: #008800 /*:root getting overwritten*/
	font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif; 
	color: var(--schriftFarbe); 
} 

.myDiv { 
	border: solid var(--schriftFarbe) 1px; 
	background-color: var(--hintergrund2); 
	border-radius: var(--radius); 
}
```