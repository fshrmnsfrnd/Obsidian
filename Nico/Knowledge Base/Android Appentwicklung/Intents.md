---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
>Ein Intent ist ein Message-Objekt, mit dem Sie eine Aktion von einer anderen App-Komponente anfordern können
# Intent-Typen 
---
### Explizite Intents
- Definiert welche App den Intent verarbeiten soll
- Paketname der App oder Klassenname wird angegeben
- Verwendung: Activity in der eigenen App starten
### Implizite Intents
- Definieren Aktion
- Bearbeitung der Aktion kann von verschiedenen Komponenten übernommen werden
# Anwendungsfälle
---
### Starten einer Aktivität
- Starten einen neuen Bildschirm (Activity) der selben App
- Kann mit oder ohne Rückgabewert gestartet werden
	- `startActivity()`
	- `startActivityForResult() -> onActivityResult()`
### Starten eines Services
- Deprecated ab API Level 21 (Seitdem Job Scheduler Objekte)
- Hintergrundservices
- `startService()`
- immer Explizite Intents verwenden
### Versenden von Broadcasts
- Kann jede App erhalten
- Systemereignisse (z.B. Akkustand)
- `sendBroadcast()`
- `sendOrderedBroadcast()`
# Intent Filter
---
- Legt fest welche Typen von Intents eine Komponente erwartet
- wird in `AndroidManifest.xml` festgelegt
- Ist ein Intent Filter definiert, kann die Activity über einen Impliziten Intent gestartet werden
# Attribute
---
### Name
- Name der zu startenden Komponente
	- **Mit** Name: Expliziter Intent
	- **Ohne** Name: Impliziter Intent
- Kann festgelegt werden mit
	- `setComponent()`
	- `setClass()`
	- `setClassName()`
	- Konstruktor
### Action
- Gibt an welche Aktion auszuführen ist
- Definiert welche Extras enthalten sind
- Aktionen zum starten einer Aktivität
	- `ACTION_VIEW`
	- `ACTION_SEND`
- Kann festgelegt werden mit
	- Konstruktor
	- `setAction()`
### Data
- Art der Daten wird i.d.R. durch Action bestimmt
- URI zu den Daten
	- `setData()`
- MIME Typ der Daten
	- `setType()`
### Category
- Es können mehrere Kategorien enthalten sein
### Extras
- Key-Value
- Einzelnes Paar: `putExtra()`
- Bundle erstellen und mit `putExtras()` hinzufügen
- Eigene Keys mit Package name
	- `static final String EXTRA_GIGAWATTS = "com.example.EXTRA_GIGAWATTS";`
### Flags
- Metadaten
# Explizite Intents
---
Beispiel: `DetailActivity`
AndroidManifest.xml
```xml
<activity android:name=".DetailActivity">
	<intent-filter>
		<action android:name="DetailActivity" />
	</intent-filter>
</activity>
```
## Andere Activity starten
MainActivity.java
```java
public void startStep1(View v){ 
	Intent i = new Intent(this,DetailActivity.class); 
	i.setAction(Intent.ACTION_VIEW); 
	startActivity(i); 
}
```
## Andere Activity starten und Werte übergeben
MainActivity.java
```java
public void startActivity(View v){ 
	Intent i = new Intent(this, DetailActivity.class); 
	i.putExtra("CALL_MESSAGE",txtInput.getText().toString()); 
	startActivity(i); 
}
```

DetailActivity.java
```java
protected void onCreate(Bundle savedInstanceState) { 
	Bundle bundle = getIntent().getExtras(); 
	txtInOut.setText(bundle.getString("CALL_MESSAGE")); 
}
```
# Andere Activity starten und Werte zurückbekommen
MainActivity.java
```java
detailLauncher = registerForActivityResult( 
	new ActivityResultContracts.StartActivityForResult(), new ActivityResultCallback() { 
		@Override 
		public void onActivityResult(ActivityResult result) { 
			if (result.getResultCode() == Activity.RESULT_OK) { 
				Intent data = result.getData(); 
				Bundle bundle = data.getExtras();
				txtInput.setText(bundle.getString("RESPONSE_MESSAGE")); 
			} 
		}
	}
);

//Auslösen per Button o.ä.
public void startActivityForResult(View v){ 
	Intent i = new Intent(this, DetailActivity.class); 
	i.putExtra("CALL_MESSAGE",txtInput.getText().toString()); detailLauncher.launch(i); 
}
```

DetailActivity.java
```java
//Auslösen per Button o.ä.
public void backWithData(View v) { 
	Intent i = new Intent(); 
	i.putExtra("RESPONSE_MESSAGE",txtInOut.getText().toString()); setResult(RESULT_OK, i); 
	super.finish(); 
}
```
# Implizite Intents
---
https://developer.android.com/guide/components/intents-common
## Beispiel: URL im Browser öffnen
AndroidManifest.xml
```xml
<!-- Berechtigung -->
<uses-permission android:name="android.permission.INTERNET"/>
```

MainActivity.java
```java
public void showUrl(View v){ 
	try{ 
		Uri webpage = Uri.parse(txtUrl.getText().toString()); 
		Intent intent = new Intent(Intent.ACTION_VIEW, webpage); 
		startActivity(intent); 
	} catch(ActivityNotFoundException e){ 
		Toast.makeText(getApplicationContext(),"Keine passende Aktivität!", 
		Toast.LENGTH_LONG).show(); 
	}
}
```
## Beispiel: Create Alarm
AndroidManifest.xml
```xml
<!-- Berechtigung -->
<uses-permission android:name="com.android.alarm.permission.SET_ALARM" />
```

MainActivity.java
```java
public void createAlarm(View v){  
    try{  
        Intent intent = new Intent(AlarmClock.ACTION_SET_ALARM)  
                .putExtra(AlarmClock.EXTRA_HOUR, 11)  
                .putExtra(AlarmClock.EXTRA_MINUTES, 5);  
        startActivity(intent);  
    }  
    catch(ActivityNotFoundException e){  
        Toast.makeText(getApplicationContext(),"Keine passende Aktivität!" ,
	        Toast.LENGTH_LONG).show();  
    }  
}
```