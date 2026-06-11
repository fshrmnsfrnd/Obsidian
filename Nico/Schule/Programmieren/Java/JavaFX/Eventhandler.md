---
Fach: "[[Programmieren]]"
Thema:
  - "[[JavaFX]]"
---
# Arten von Eventhandlern
---

| Name der Eventklasse | Beschreibung                                                                                                       |
| -------------------- | ------------------------------------------------------------------------------------------------------------------ |
| ActionEvent          | Standard-Event vieler Steuerelemente, zum Beispiele Mausklick auf einen Button                                     |
|                      | Event-Typ: ACTION                                                                                                  |
| KeyEvent             | Tastendruck auf der Tastatur                                                                                       |
|                      | Event-Typen: KEY_TYPED, KEY_PRESSED, KEY_RELEASED                                                                  |
| MouseEvent           | Bewegung der Maus oder Druck auf eine Maustaste                                                                    |
|                      | Event-Typen: MOUSE_CLICKED, MOUSE_DRAGGED, MOUSE_ENTERED, MOUSE_EXITED, MOUSE_MOVED, MOUSE_PRESSED, MOUSE_RELEASED |
# Innere Eventhandler Klasse
---
>Dies ist die einzige Möglichkeit, mit der ein Eventhandler mehrfach verwendet werden kann
```java
class Handler implements EventHandler<ActionEvent> {
	@Override
	public void handle(ActionEvent t){
		//Do Something
	}
}

object.addEventHandler(ActionEvent.ACTION, new Handler());
```
Die Handler Klasse wird dabei in der Klasse `App` erstellt und den Eventhandler hinzuzufügen in der Methode `start` wo auch das Element erstellt wird
# Innere anonyme Klasse
---
```java
object.addEventHandler(ActionEvent.ACTION, new EventHandler<ActionEvent>() { 
	@Override 
	public void handle(ActionEvent event) { 
		//Do Something 
	} 
});
```
# Set Methoden
---
```java
object.setOnAction(new EventHandler<ActionEvent>() { 
	@Override 
	public void handle(ActionEvent event) { 
		//Do Something 
	}
});
```