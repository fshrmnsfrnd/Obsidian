---
Fach: "[[Programmieren]]"
Thema:
  - "[[FXML]]"
---
scDie Methode initialize() in der Controller Klasse wird beim erstellen der Oberfläche ausgeführt. 
```java
public class TemplateController{
	@FXML
    private TextField textField;
@FXML
    public void initialize() {
	    textField.setText("Hallo World");
    }
}
```

## Beispiel Combobox (Dropdown)
```java
package gui;

import javafx.fxml.FXML;
import javafx.scene.control.ComboBox;
import javafx.scene.control.TextField;

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.HashMap;
import javafx.event.ActionEvent;

public class TemplateController{
    @FXML
    private ComboBox<String> comboBox;
    @FXML
    private TextField textField;
    private final HashMap<String, String> staaten = new HashMap<>();

    public void initialize() {
        ladeDatei();
        comboBox.getItems().addAll(staaten.keySet());
    }

    private void ladeDatei() {
        try (BufferedReader br = new BufferedReader(new FileReader("staaten.csv"))) {
            String zeile;
            while ((zeile = br.readLine()) != null) {
                String[] teile = zeile.replace("\"", "").split(";");
                if (teile.length == 2) {
                    staaten.put(teile[0], teile[1]);
                }
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

    @FXML
    private void updateTextField(ActionEvent event) {
        String kuerzel = comboBox.getValue();
            if (kuerzel != null) {
                textField.setText(staaten.get(kuerzel));
            }
    }
}

```