---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
# View Eventlistener
---

| Event                         | Description                                                                                 |
| ----------------------------- | ------------------------------------------------------------------------------------------- |
| `onClickListener`             | Wird verwendet, um die kurze Berührung eines [[Views]] zu erkennen.                             |
| `onCreateContextMenuListener` | Wartet auf die Erstellung eines Kontextmenüs als Ergebnis eines langen Klicks.              |
| `onDragListener`              | Wird verwendet, wenn [[Views]] von einer Position zu einer zweiten gezogen werden.              |
| ``onFocusChangedListener``    | Erkennt, wenn sich der Fokus als Ergebnis einer Interaktion ändert.                         |
| ``onGenericMotionEvent``      | Verwendung unterschiedlicher Gesten.                                                        |
| `onHoverListener`             | Erkennt Bewegungen über einem View. Wird nicht bei Smartphones ausgelöst.                   |
| `onKeyListener`               | Wird verwendet, ob eine Taste gedrückt wurde. Wird nicht ausgelöst bei einem SmartKeyboard. |
| `onLongClickListener`         | Ein View wird für längere Zeit berührt.                                                     |
| `onTouchListener`             | Berührung eines [[Views]] mit einem oder mehreren Berührpunkten oder mittels Gestenbewegungen.  |
# Listener mit Anonymen Objekt
---
```java
public class MainActivity extends AppCompatActivity { 
	ActivityMainBinding binding; 
	... 
	protected void onCreate(Bundle savedInstanceState) {
	...
		binding.btnEvents.setOnClickListener( 
			new Button.OnClickListener(){ 
				@Override 
				public void onClick(View v) { 
					if (!binding.btnEvents.getText().equals("Click me!")){
						binding.btnEvents.setText("Click me!"); 
					} else { 
						binding.btnEvents.setText("Clicked"); 
					}
				}
			}
		);
		...
	}
	...
}
```
# Listener mit Eventhandler-Klasse
---
```java
public class MainActivity extends AppCompatActivity { 
	ActivityMainBinding binding; 
	... 
	protected void onCreate(Bundle savedInstanceState){ 
		...  
		binding.btnEvents.setOnClickListener(new EventHandlers()); 
		... 
	} 
	private class EventHandlers implements Button.OnClickListener{ 
		@Override 
		public void onClick(View v) { 
			if (!binding.btnEvents.getText().equals("Click me!")) {
				binding.btnEvents.setText("Click me!"); 
			} else { 
				binding.btnEvents.setText("Clicked");
			}
		}
		...
	}
	...
}
```
# Listener mit Activity-Klasse
---
```java
public class MainActivity extends AppCompatActivity implements Button.OnClickListener{
	ActivityMainBinding binding;
	...
	protected void onCreate(Bundle savedInstanceState) {
		...
		binding.btnEvents.setOnClickListener(this);
		...
	}
	@Override
	public void onClick(View v) {
		if (!binding.btnEvents.getText().equals("Click me!")) {
			binding.btnEvents.setText("Click me!");
		} else {
			binding.btnEvents.setText("Clicked");
		}
	}
}
```
# Listener mit Lambda Funktion
```java
public class MainActivity extends AppCompatActivity implements Button.OnClickListener{
	ActivityMainBinding binding;
	...
	protected void onCreate(Bundle savedInstanceState) {
		...
		binding.btnEvents.setOnClickListener.setOnClickListener(view -> {
			//Do Somathing
		});
	}
}
```