---
Fach:
tags:
Thema:
  - "[[CSS]]"
  - "[[Webentwicklung]]"
---
 Floating Boxes sind heute durch Flexboxen oder Grid abgelöst.
> [!IMPORTANT] Nicht die äußere Container muss `float` haben, sondern die inneren Elemente selbst
# Positionen
| CSS             | Beschreibung                                                                    |
| --------------- | ------------------------------------------------------------------------------- |
| `float:left`    | An der nächsten freien Stelle links anschließen                                 |
| `float:right`   | An der nächsten freien Stelle rechts anschließen.                               |
| `float:none`    | Kein Textumfluss                                                                |
| `float:inherit` | Positionierung wie das Elternelement                                            |
| `clear: left`   | Der neue Inhalt kann sich nicht an eine links-floatende Box nicht anschließen.  |
| `clear: right`  | Der neue Inhalt kann sich nicht an eine rechts-floatende Box nicht anschließen. |
| `clear: both`   | Der neue Inhalt wird in einer neuen Zeile angeordnet.                           |
> [!IMPORTANT] `clear` kann nur das **eigene** floating aufheben, wenn das nächste Kästchen auch z.B. `float: left` hat, kann man dagegen nichts machen, das muss dann im nächsten Kästchen passieren
### Beispiel
```html
<div class="aussen">
	<div>
		<img src="bild.img">
	</div>
	<div>
		<img src="bild2.img">
	</div>
</div>
```

```css
.aussen>div{
	box-sizing: border-box;
	width: 23%;
	float: left;
	margin: 1%;
}

.aussen>div>img{
	width: 95%;
	margin: 2.5% 2.5%;
}
```