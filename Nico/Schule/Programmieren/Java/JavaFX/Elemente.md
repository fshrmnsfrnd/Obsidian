---
Thema:
  - "[[JavaFX]]"
---
# Button  
---
https://docs.oracle.com/javafx/2/ui_controls/button.htm#CJHEEACB  

`Button button = new Button("Accept");`  
`button.setOnAction(e -> System.out.println("Clicked"));`

**Mit Bild:**  
```java
Image imageDecline = new Image(getClass().getResourceAsStream("not.png"));
Button imgButton = new Button();
imgButton.setGraphic(new ImageView(imageDecline));
```
# RadioButton  
---
https://docs.oracle.com/javafx/2/ui_controls/radio-button.htm#BABBJBDA  

`RadioButton rb = new RadioButton("Calendar")`  
`rb.setSelected(true);`  
`rb.isSelected();`
## ToggleGroup  

`radioButton.setToggleGroup(toggleGroup)`  
`toggleGroup.getSelectedToggle();`  
`toggleGroup.selectToggle(radioButton);`
# Label  
---
https://docs.oracle.com/javafx/2/ui_controls/label.htm#CIHHFIBJ  

`label.setText("Neuer Text");`  
`label.getText();`
# TextField  
---
https://docs.oracle.com/javafx/2/ui_controls/text-field.htm#BABBCEIG  

`textField.setText("Hallo");`  
`String value = textField.getText();`  
`textField.clear();`
# Spinner  
---
`Spinner spinner = new Spinner(min, max, start)`  
`spinner.getValue();`  
`spinner.setValueFactory(new SpinnerValueFactory.IntegerSpinnerValueFactory(min, max));`
# ToggleButton  
---
https://docs.oracle.com/javafx/2/ui_controls/toggle-button.htm#CACJDICF  

`toggleButton.setSelected(true);`  
`toggleButton.isSelected();`
# Checkbox    
---
https://docs.oracle.com/javafx/2/ui_controls/checkbox.htm#CHDFEJCD  

`checkBox.setSelected(true);`  
`checkBox.isSelected();`
# ChoiceBox  
---
https://docs.oracle.com/javafx/2/ui_controls/choice-box.htm#BCEDJAEH  

`choiceBox.getItems().addAll("A", "B");`  
`choiceBox.setValue("A");`  
`choiceBox.getValue();`
# PasswordField    
---
https://docs.oracle.com/javafx/2/ui_controls/password-field.htm#CHDIAAAJ  

`passwordField.setText("1234");`  
`String pw = passwordField.getText();`
# ScrollBar  
---
https://docs.oracle.com/javafx/2/ui_controls/scrollbar.htm#BGBEGJDE  

`scrollBar.setMin(0);`  
`scrollBar.setMax(100);`  
`scrollBar.setValue(50);`  
`double val = scrollBar.getValue();`
# ScrollPane  
---
https://docs.oracle.com/javafx/2/ui_controls/scrollpane.htm#CBBFFBCH  

`scrollPane.setContent(node);`  
`scrollPane.setVvalue(0.5);`  
`scrollPane.setHvalue(0.0);`
# ListView  
---
https://docs.oracle.com/javafx/2/ui_controls/list-view.htm#CEGGEDBF  

`listView.getItems().addAll("Item 1", "Item 2");`  
`listView.getSelectionModel().getSelectedItem();`
# TableView  
---
https://docs.oracle.com/javafx/2/ui_controls/table-view.htm#CJAGAAEE  

`tableView.getItems().add(item);`  
`tableView.getSelectionModel().getSelectedItem();`
# TreeView  
---
https://docs.oracle.com/javafx/2/ui_controls/tree-view.htm#BABDEADA  

`treeView.getSelectionModel().getSelectedItem();`  
`treeView.getRoot();`
# ComboBox  
---
https://docs.oracle.com/javafx/2/ui_controls/combo-box.htm#BABJCCIB  

`comboBox.getItems().addAll("X", "Y");`  
`comboBox.setValue("X");`  
`comboBox.getValue();`
# Separator  
---
https://docs.oracle.com/javafx/2/ui_controls/separator.htm#BGBCFDFI  

`separator.setOrientation(Orientation.HORIZONTAL);`
# Slider  
---
https://docs.oracle.com/javafx/2/ui_controls/slider.htm#CCHFBJCH  

`slider.setMin(0);`  
`slider.setMax(100);`  
`slider.setValue(50);`  
`double val = slider.getValue();`  
`slider.setShowTickMarks(true);`  
`slider.setShowTickLabels(true);`
# ProgressBar  
---
https://docs.oracle.com/javafx/2/ui_controls/progress.htm#CHDDJAJE  

`progressBar.setProgress(0.5);`  
`double value = progressBar.getProgress();`
# Hyperlink  
---
https://docs.oracle.com/javafx/2/ui_controls/hyperlink.htm#CIHGADBG  

`hyperlink.setOnAction(e -> openLink());`  
`hyperlink.setText("Click me");`
# Tooltip  
---
https://docs.oracle.com/javafx/2/ui_controls/tooltip.htm#BABBIJBJ  

`Tooltip tooltip = new Tooltip("Info");`  
`Tooltip.install(node, tooltip);`
# HTMLEditor  
---
https://docs.oracle.com/javafx/2/ui_controls/editor.htm#CHDBEGDD  

`String html = htmlEditor.getHtmlText();`  
`htmlEditor.setHtmlText("<b>Text</b>");`
# TitlePane 
---
https://docs.oracle.com/javafx/2/ui_controls/accordion-titledpane.htm#CACGBAHI  

`titledPane.setExpanded(true);`  
`titledPane.setText("Titel");`  
`titledPane.setContent(node);`
# Menu  
---
https://docs.oracle.com/javafx/2/ui_controls/menu_controls.htm#BABGHADI  

`Menu menu = new Menu("Datei");`  
`MenuItem item = new MenuItem("Öffnen");`  
`menu.getItems().add(item);`
# ColorPicker  
---
https://docs.oracle.com/javafx/2/ui_controls/color-picker.htm#BABHFGHA  

`Color color = colorPicker.getValue();`  
`colorPicker.setValue(Color.RED);`
# PaginationControl  
---
https://docs.oracle.com/javafx/2/ui_controls/pagination.htm#CACJCAGB  

`pagination.setPageFactory(pageIndex -> createPage(pageIndex));`  
`pagination.setPageCount(10);`
# FileChooser  
---
https://docs.oracle.com/javafx/2/ui_controls/file-chooser.htm#CCHICECF  

`FileChooser fc = new FileChooser();`  
`File file = fc.showOpenDialog(stage);`