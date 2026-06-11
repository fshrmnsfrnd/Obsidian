---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
Snackbars sind [[Toasts]] die nicht einfach nur Text anzeigen, sondern auch gelayoutet werden können, und Interaktionen enthalten können. 

Eine Snackbar ist ein `FrameLayout`

Wenn in der `activity.xml` bereits andere Layouts sind, sollten diese in ein `CoordinatorLayout` gepackt werden:
```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.coordinatorlayout.widget.CoordinatorLayout 
	xmlns:android="http://schemas.android.com/apk/res/android"
	xmlns:app="http://schemas.android.com/apk/res-auto"
	android:id="@+id/coordinatorL"
	android:layout_width="match_parent"
	android:layout_height="match_parent">
	
	<androidx.constraintlayout.widget.ConstraintLayout
		android:layout_width="match_parent"
		android:layout_height="match_parent">
		<TextViewOrAnythingElse/>
	</androidx.constraintlayout.widget.ConstraintLayout>
</androidx.coordinatorlayout.widget.CoordinatorLayout>
```

# Erzeugen und Anzeigen
---
**Ausführlich:**
```java
CoordinatorLayout view = findViewById(R.id.myCoordinatorLayout);
int stringId = R.string.info_message; 
int duration = Snackbar.LENGTH_SHORT; 
Snackbar mySnackbar = Snackbar.make(view, stringId, duration);
mySnackbar.show();
```

**Kurz:**
```java
Snackbar.make(findViewById(R.id.myCoordinatorLayout), R.string.info_message,
	Snackbar.LENGTH_SHORT).show();
```

# Snackbar mit Benutzerinteraktion
---
```java
Snackbar mySnackbar = Snackbar.make(findViewById(R.id.myCoordinatorLayout),
	R.string.info_message, Snackbar.LENGTH_INDEFINITE);

//Auf Events Reagieren
mySnackbar.addCallback(
	new Snackbar.Callback() { 
		@Override 
		public void onShown(Snackbar sb) { 
			// Code der beim Anzeigen ausgeführt wird 
		} 
		@Override 
		public void onDismissed(Snackbar transientBottomBar, int event) { 
			// Code der beim Ausblenden angezeigt wird
		} 
	}
); 

//Buttons hinzufügen (Nur eine Action möglich, kann mit einem weiteren .setAction 
//überschrieben werden)
mySnackbar.setAction("Rückgängig", 
	new View.OnClickListener(){ 
		@Override 
		public void onClick(View v) { 
			//Hier steht der Code, der irgendetwas rückgängig macht. 
		} 
	}
); 

mySnackbar.show();
```
Der Parameter `event` kann folgende konstante Werte enthalten: 
`Snackbar.Callback.DISMISS_EVENT_ACTION`: Durch Aktion geschlossen
`Snackbar.Callback.DISMISS_EVENT_TIMEOUT`: Automatisch abgelaufen  
`Snackbar.Callback.DISMISS_EVENT_SWIPE`: Vom Benutzer weggeswiped
`Snackbar.Callback.DISMISS_EVENT_MANUAL`: Manuell geschlossen 
`Snackbar.Callback.DISMISS_EVENT_CONSECUTIVE`: Von neuer Snackbar ersetzt

