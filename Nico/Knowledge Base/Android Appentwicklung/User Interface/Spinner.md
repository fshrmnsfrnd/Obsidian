---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
In der `.xml` einen `Spinner` einfügen

# Statisch Werte einfügen
---
1. **Spinner erstellen**
Entweder in einen Container "Spinner" in das Layout ziehen 
oder den Spinner von Hand in die `activity.xml` schreiben:
```xml
<Spinner  
	android:id="@+is/spinnerID"  
	android:layout_width=""  
	android:layout_height="wrap_content"    
/>
```

2. **Werte erstellen**
`res/values/strings.xml`
```xml
<resources>  
	<string name="app_name">UISpinner</string>  
	<string-array name="tempCalTypes">  
		<item>C° in F°</item>  
		<item>C° in K</item>  
		<item>F° in C°</item>  
		<item>F° in K°</item>  
		<item>K in C°</item>  
		<item>K in F°</item>  
	</string-array>  
</resources>
```

3. **Spinner mit Werten füllen**
`MainActivity.java`
```java
// 1. Referenz auf Spinner herstellen  
Spinner spinner = (Spinner) findViewById(R.id.spinnerID);  
// 2. Erzeugen des Adapters  
ArrayAdapter<CharSequence> adapter = ArrayAdapter.createFromResource(
	this,R.array.tempCalTypes, android.R.layout.simple_spinner_item
);  

@Override
protected void onCreate(Bundle savedInstanceState){
	// 3. Festlegen der Darstellung  
	adapter.setDropDownViewResource(  
		android.R.layout.simple_spinner_dropdown_item
	);  
	//4. Spinner mit Adapter verknüpfen  
	spinner.setAdapter(adapter);
}
```

# Dynamisch Werte hinzufügen
---
`MainActivity.java`
```java
// 1. Referenz auf Spinner herstellen  
Spinner spinner = (Spinner) findViewById(R.id.spinnerID);  
// 2. dynamische Daten generieren (Simulation)  
ArrayList<String> list = new ArrayList<>();  
list.add("C° in F°");  
...   
ArrayAdapter<String> adapter = new ArrayAdapter<>(
	this,android.R.layout.simple_spinner_item,list
);  
adapter.setDropDownViewResource(  
	android.R.layout.simple_spinner_dropdown_item
);  
spinner.setAdapter(adapter);
```

# Auf Aktionen reagieren (EventHandler)
---
```java
public class MainActivity extends AppCompatActivity implements AdapterView.OnItemSelectedListener {  
	protected void onCreate(Bundle savedInstanceState){
		...
		spinnerBild.setOnItemSelectedListener(this);
	}
	@Override  
	public void onItemSelected(AdapterView<?> parent, View view, int position,long id){ 
		String output;
		output = parent.getItemAtPosition(position).toString();
		blOutput.setText(output);
	}
	
	@Override  
	public void onNothingSelected(AdapterView<?> parent) {  
		//leere Implementierung  
	}
}
```

# Ausgewählten Wert verwenden
```java
Spinner inputBaumArt = findViewById(R.id.spinnerID);
String baumArt = inputBaumArt.getSelectedItem().toString();
```