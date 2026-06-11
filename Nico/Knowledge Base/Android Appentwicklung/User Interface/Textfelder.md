---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
# Arten von Textfeldern
---

> [!NOTE] Es wird immer die passende Tastatur am Display angezeigt und falsche Eingaben gesperrt

| Name                | Descripton          |
| ------------------- | ------------------- |
| `PlainText`         | Einfacher Text      |
| `Password`          | Maskierter Text     |
| `Password(Numeric)` | Maskierte Zahlen    |
| `E-Mail`            | Email Adresse       |
| `Phone`             | Telefonnummer       |
| `Postal Address`    | Postalische Adresse |
| `MultilineText`     | Mehrzeiliger Text   |
| `Time`              | Zeit                |
| `Date`              | Datum               |
| `Number`            | Positive Ganzzahlen |
| `Number(Signed)`    | Alle Ganzzahlen     |
| `Number(Decimal)`   | Kommazahlen         |
# Eigenschaften
---
**Autokorrektur Aktivieren:** 
```xml
<EditText
	android:inputType="textCapSentences|textAutoCorrect"
/>
```
**Passwort im Passwortfeld anzeigen**
```xml
<EditText
	android:inputType="TYPE_CLASS_TEXT|TYPE_TEXT_VARIATION_VISIBLE_PASSWORD"
/>
```
**Mehrzeiliges Adressfeld mit automatisch großen Wörtern**
```xml
<EditText
	android:inputType="TYPE_CLASS_TEXT|TYPE_TEXT_VARIATION_POSTAL_ADDRESS
						|TYPE_TEXT_FLAG_MULTI_LINE"
/>
```
**Zeit Eingabe**
```xml
<EditText
	android:inputType="TYPE_CLASS_DATETIME | TYPE_DATETIME_VARIATION_TIME"
/>
```
# Bestätigungstaste
---
Um ein passendes Icon anzuzeigen:
```xml
<EditText 
	android:inputType="text" 
	android:imeOptions="actionNext|actionDone|actionGo|actionSearch|actionSend|uvm." 
/>
```

Hiermit wird `OnEditorAction` ausgelöst. Darauf reagieren kann man folgendermaßen:
```java
EditText editText = (EditText) findViewById(R.id.search); editText.setOnEditorActionListener(new TextView.OnEditorActionListener() { 
	@Override 
	public boolean onEditorAction(TextView v, int actionId, KeyEvent event) { 
		boolean handled = false; 
		if (actionId == EditorInfo.IME_ACTION_NEXT) { 
			sendMessage(); 
			handled = true; 
		} 
		return handled; 
	} 
});
```
# Autovervollständigung
---
activity.xml
```xml
<AutoCompleteTextView
	android:id="@+id/txtInputTree"
	...
	android:text="AutoCompleteTextView"
/>
```

/res/values/strings.xml
```xml
<resources>
	<string-array name="trees">
		<item>Ahorn</item>
		...
		<item>Zeder</item>
	</string-array>
</resources>
```

xxx.java
```java
AutoCompleteTextView txtInputTree; 
txtInputTree = (AutoCompleteTextView) findViewById(R.id.txtInputTree); 
String[] trees = getResources().getStringArray(R.array.trees); 
ArrayAdapter adapter = new ArrayAdapter(this, android.R.layout.simple_list_item_1,trees); 
txtInputTree.setAdapter(adapter);
```
