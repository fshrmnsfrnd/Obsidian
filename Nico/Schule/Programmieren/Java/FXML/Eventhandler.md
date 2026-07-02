---
Thema:
  - "[[FXML]]"
---
# Im Element
---
Um auf das Element zugreifen zu können muss im SceneBuilder unter `Code` die `fx:id` festgelegt werden.

Hier kann auch die Methode ausgewählt werden die bei einem Event ausgeführt werden soll.
# Controller
---
In NetBeans einfach rechtsklick auf die FXML Datei -> Make Controller.
Dies verbindet automatisch den Controller mit der FXML.

Wenn bereits Eventlistener in der FXML deklariert sind, werde diese automatisch erstellt.

Werden nach dem erstellen des Controllers nochmal Dinge in der FXML geändert, einfach nochmal Make Controller ausführen, alle neuen Nodes und Eventlistener werden hinzugefügt.