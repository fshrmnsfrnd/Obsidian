---
Thema:
  - "[[Java]]"
  - "[[JavaFX]]"
---
# Basisaufbau

Es wird ein **Java with Maven / Simple JavaFX Maven Archetype(Gluon)** Projekt erzeugt

```java
public class App extends Application {
	//EventListeners
    @Override
    public void start(Stage stage) {
		BorderPane root = new BorderPane(); //Oder GridPane
		
		Button element1 = new Button();
		root.setBottom(element1);

		var scene = new Scene(root, 640, 480);

		stage.setScene(scene);
		stage.show();
	}
	public static void main(String[] args) {
        launch();
    }
}
```

Es als `root`, also Basislayout muss eines [[Layouts|dieser hier]] verwendet werden.

Darin können dann die [[Elemente]] verwendet werden. 

[[Schule/Programmieren/Java/JavaFX/Eventhandler]] 