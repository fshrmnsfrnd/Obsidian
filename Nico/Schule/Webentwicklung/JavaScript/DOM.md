---
tags:
Thema:
  - "[[HTML]]"
  - "[[JavaScript]]"
  - "[[Webentwicklung]]"
---
>Document Object Model

# Zugriff auf Elemente
---

| Methode                           | Beschreibung                                                                                                                                                           |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `getElementById('idname')`        | Liefert das DOM-Objekt zurück, das die id 'idname' hat. Je nach zurückgeliefertem Objekt stehen zur Programmierung dessen Attribute und Methoden zur Verfügung.        |
| `getElementsByName('name')`       | Liefert eine **HTMLCollection** aus Objekten mit dem übergebenen Wert für das Attribut name zurück. Auf die einzelnen Elemente kann über den index zugegriffen werden. |
| `getElementsByTagName('tagname')` | Liefert eine **HTMLCollection** aus Objekten zu dem übergebenen tag. Auf die einzelnen Elemente kann über den index zugegriffen werden.                                |
| `querySelector('cssselector')`    | Liefert das **1. Element** des DOM Baumes, die mit dem übergebenen CSS-Selektor ausgewählt werden.                                                                     |
| `querySelectorAll('cssselector')` | Liefert eine **NodeList** mit Elementen des DOM Baumes, die mit dem übergebenen CSS-Selektor ausgewählt werden.                                                        |
# Document Attribute
---

| Attribut             | Beschreibung                         |
| -------------------- | ------------------------------------ |
| `document.images[]`  | HTMLCollection mit allen Bildern.    |
| `document.forms[]`   | HTMLCollection mit allen Formularen. |
| `document.links[]`   | HTMLCollection mit allen Links.      |
| `document.anchors[]` | HTMLCollection mit allen Ankern.     |
# Navigieren durch das DOM
---

| Attribut       | Beschreibung                                          |
| -------------- | ----------------------------------------------------- |
| `childNodes[]` | HTMLCollection mit allen Kind-Elementen (child Nodes) |
| `parentNode`   | Referenz zum übergeordneten Element                   |
![[Pasted image 20260201231701.png]]

# Manipulation des DOM
---
## HTML einfügen
```js
document.getElementById("main").innerHTML = "Heading";
//oder
document.getElementById("main").innerHTML = "<div><h1>Heading</h1></div>";
```
## Attribute von Elementen ändern
```js
document.getElementById("bild1").src = "bild1.jpg"; // Bild ändern 
document.getElementById("link1").href = "http://www.ts-muenchen.de"; // Linkziel ändern 
document.getElementById("zeile").classList.add("row"); // CSS-Klasse ändern
document.getElementById("element").style.color = "#0000ff"; // CSS-Style ändern
```
## HTML Element erstellen
```js
let newNode = document.createElement("div")
document.getElementById("id").appendChild(newNode)
document.getElementById("id").insertBefore(newNode, child)
```
### Snippet Tabelle Erzeugen
```js
let tabelle = document.createElement("table"); 
for (let i= 0; i < 10 ; i++) { 
	let zeile = document.createElement("tr"); 
	tabelle.appendChild(zeile); 
	for (j = 0; j < 4; j++) { 
		let spalte = document.createElement("td");
		spalte.innerHTML = "Zeile "+i+" ,Spalte "+j; 
		zeile.appendChild(spalte); 
	} 
} 
document.getElementById("kaestchen").appendChild(tabelle);
```