---
Fach:
Thema:
  - "[[JavaScript]]"
  - "[[Webentwicklung]]"
---
# Events
| Event-Handler | Beschreibung                                |
| ------------- | ------------------------------------------- |
| `change`      | bei erfolgter Änderung                      |
| `click`       | beim Anklicken                              |
| `dblclick`    | bei doppeltem Anklicken error im Fehlerfall |
| `focus`       | beim Aktivieren                             |
| `keydown`     | bei gedrückter Taste                        |
| `keyup`       | bei losgelassener Taste                     |
| `load`        | beim Laden einer Datei                      |
| `mousedown`   | bei gedrückter Maustaste                    |
| `mousemove`   | bei weiterbewegter Maus                     |
| `mouseout`    | beim Verlassen des Elements mit der Maus    |
| `mouseover`   | beim Überfahren des Elements mit der Maus   |
| `mouseup`     | bei losgelassener Maustaste                 |
| `reset`       | beim Zurücksetzen des Formulars             |
| `select`      | beim Selektieren von Text                   |
| `submit`      | beim Absenden des Formulars                 |
# Einbinden
## im HTML
```html
<button onClick="clkAction()">Do Something</button>
```
## In JavaScript
```js
document.getElementById("id").addEventListener("click",myFunc.bind(event));

document.getElementById("id").addEventListener("click",(e) => {
		e.type        // "click"
	    e.target      // Element, das geklickt wurde
	    e.currentTarget // Element mit dem Listener
	    e.clientX    // Mausposition X
	    e.clientY    // Mausposition Y
	}
);

document.addEventListener("keydown", (e) => {
    console.log(e.key);      // z. B. "Enter"
    console.log(e.code);     // z. B. "Enter"
});
```

