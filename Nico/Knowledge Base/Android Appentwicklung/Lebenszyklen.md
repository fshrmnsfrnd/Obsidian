---
tags:
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
https://developer.android.com/guide/components/activities/activity-lifecycle?hl=de

![[Pasted image 20251014092354.png]]
# Zustände
---
Daten müssen zu geeigneten Zeitpunkten gespeichert werden.

## Persistenter Zustand
Daten, die z.B. in einer lokalen Datenbank gespeichert werden sind persistente Daten. Sie bleiben bestehen, auch wenn die Laufzeit beendet wird.

## Dynamischer Zustand
Wird auch als Instanz-Zustand bezeichnet. Dynamische Daten werden gelöscht wenn RAM Speicher benötigt wird oder die Laufzeit beendet wird

# Event Functions überschreiben
---
Um die Event Functions (z.B. `onPause()`, `onStop()` usw.) zu überschreiben:
```java
public class MainActivity extends AppCompatActivity {
	@Override  
	protected void onStop(){  
	    super.onStop();
	    //Code der beim stoppen ausgeführt werden soll
	}
}
```

# App Daten persistent speichern
---
`onSaveInstanceState` und `onRestoreInstanceState` überschreiben:

```java
public class MainActivity extends AppCompatActivity {
...
	@Override protected void onSaveInstanceState(@NonNull Bundle outState) { 
		super.onSaveInstanceState(outState); 
		outState.putInt("<Name>", <Value>); 
	}

	@Override 
	protected void onRestoreInstanceState(@NonNull Bundle savedInstanceState) {
		super.onRestoreInstanceState(savedInstanceState); 
		clicks = savedInstanceState.getInt("<Name>"); 
	}
...
}
```
