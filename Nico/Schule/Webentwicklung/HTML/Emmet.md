---
Thema:
  - "[[HTML]]"
  - "[[Webentwicklung]]"
---
https://docs.emmet.io/cheat-sheet/
# Kind Elemente
`div>p`:
```html
<div>
	<p></p>
</div>
```
# Klassen
`element.classname`:
```html
<element class="classname"></element>
```
# ID
`element#idname`:
```html
<element id="idname"></element>
```
# Beliebige Eigenschaft
`div[title=item]`:
```html
<div title="item"></div>
```
# Sibling
`div+p`:
```html
<div></div>
<p></p>
```
# Mehrere Elemente
`div*3`:
```html
<div></div>
<div></div>
<div></div>
```
# Nummerieren
## aufsteigend
`span.id$$*3` :
```html
<span id="01"></span>
<span id="02"></span>
<span id="03"></span>
```
## absteigend
`span.id$@-*3` :
```html
<span id="3"></span>
<span id="2"></span>
<span id="1"></span>
```
## beginnen ab
`span.id$@5*3`
```html
<span id="05"></span>
<span id="06"></span>
<span id="07"></span>
```
# Text (inner HTML)
`p{Inhalt}`
```html
<p>Inhalt</p>
```
# HTML Abkürzungen
## Grundstruktur
Emmet: `!`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
</body>
</html>
```


| Emmet   | HTML                              |
| ------- | --------------------------------- |
| element | `<element></element>`             |
| a       | `<a href=""></a>`                 |
| link    | `<link rel="stylesheet" href="">` |
