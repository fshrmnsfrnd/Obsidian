---
Thema:
  - "[[FXML]]"
---
# FXML Tabellen
---
## Befüllen (Fixe Spalten)
```java
@FXML
TableView<Sportart> tblSportarten;

TableColumn col1 = (TableColumn) tblSportarten.getColumns().get(0);
col1.setCellValueFactory(new PropertyValueFactory<>("sport_Id"));

TableColumn col2 = (TableColumn) tblSportarten.getColumns().get(1);
col2.setCellValueFactory(new PropertyValueFactory<>("sportart"));

TableColumn col3 = (TableColumn) tblSportarten.getColumns().get(2);
col3.setCellValueFactory(new PropertyValueFactory<>("beitrag"));

tblSportarten.getItems().clear();

try{
	ArrayList<Sportart> sportarten = SportartDAO.getAll();
	for (Sportart o:sportarten){
		tblSportarten.getItems().add(o);
	}
}catch(SQLException e){
	App.showAlert("Error", "LoadSportart", e.getMessage());
}
```

## Befüllen (dynamische Spalten)
```java
try {
	tblResults.getItems().clear();
	tblResults.getColumns().clear();

	//Abfrage starten
	ResultSet rs = Dao.executeQuery(txtSQL.getText());

	//Metadaten auswerten
	int colCount = rs.getMetaData().getColumnCount();

	//Create Result-Columns
	for (int i = 1; i <= colCount; i++) {
		TableColumn col = new TableColumn(rs.getMetaData().getColumnName(i));
		col.setCellValueFactory(new MapValueFactory<>("col" + i));
		tblResults.getColumns().add(col);
	}

	//Loop Data and fill Data-Items
	ObservableList<Map<String, Object>> items = FXCollections.<Map<String, Object>>observableArrayList();

	while (rs.next()) {
		Map<String, Object> item = new HashMap<>();
		String value = "";

		for (int i = 1; i <= colCount; i++) {

			value = "";

			switch (rs.getMetaData().getColumnType(i)) {
				case Types.BOOLEAN:
					value = String.valueOf(rs.getBoolean(i));
					break;
				case Types.DATE:
					value = String.valueOf(rs.getDate(i));
					break;
				case Types.REAL:
				case Types.DECIMAL:
				case Types.NUMERIC:
				case Types.DOUBLE:
					value = String.valueOf(rs.getDouble(i));
					break;
				case Types.FLOAT:
					value = String.valueOf(rs.getFloat(i));
					break;
				case Types.TINYINT:
				case Types.SMALLINT:
				case Types.INTEGER:
					value = String.valueOf(rs.getInt(i));
					break;
				case Types.TIMESTAMP:
					value = String.valueOf(rs.getTimestamp(i));
					break;
				case Types.LONGVARCHAR:
				case Types.VARCHAR:
					value = rs.getString(i);
					break;
			}
			item.put("col" + i, value);
		}
		items.add(item);
	}
	tblResults.getItems().addAll(items);
} catch (Exception e) {
	System.out.println(e.getLocalizedMessage());
}
```
# FXML neue Seite anzeigen
---
```java
try{
	// FXML-Loader erzeugen und Layout auswählen
	FXMLLoader loader = new FXMLLoader();
	loader.setLocation(App.class.getResource("main.fxml"));
	// Root der neuen Scene speichern
	Parent root = loader.load();
	
	//aktuellen Controller von main.xml holen und stage übergeben
	MainController controller = loader.getController();
	controller.setStage(stage);
	
	//Neue Szene erzeugen und Root-Element übergeben
	Scene scene = new Scene(root);
	
	//Die Szene der Stage austauschen und 
	stage.setScene(scene);
	stage.show();

}catch (IOException e){
	System.out.println(e.getLocalizedMessage());
}
```
# FXML Aufklappmenü
---
Im SceneBuilder erstellen:
```
MenuBar(
	Menu(
		MenuItem("Item1"), 
		MenuItem("Item2")
	)
)
```
# FXML Selected Item von Tabelle
---
Eintragen bei `onMouseClicked` beim `TableView`
```java
@FXML
public void selectItem() {
	Sportart selected = (Sportart) tblSportarten.getSelectionModel().getSelectedItem();

	txtSportId.setText(Integer.toString(selected.getSport_Id()));
	txtSportart.setText(selected.getSportart());
	txtBeitrag.setText(Float.toString(selected.getBeitrag()));
}
```