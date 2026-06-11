---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
```java
binding.myLayout.setOnTouchListener( 
	new ConstraintLayout.OnTouchListener() { 
		public boolean onTouch(View v, MotionEvent m){ 
			int pointerCount = m.getPointerCount(); 
			int pointerId = m.getPointerId(0); 
			int pointerIndex = m.findPointerIndex(pointerId);
			...
			return true;
		}
	}
);
```

> [!NOTE] Return Wert
> Ist der Rückgabewert der `onTouch()`-Methode `true` bedeutet das, dass das Event nicht verarbeitet wurde und weitergereicht wird. Ist der Rückgabewert `false`, wurde das Event verarbeitet und ist damit beendet.
### Beispiel
```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
	xmlns:android="http://schemas.android.com/apk/res/android"
	xmlns:app="http://schemas.android.com/apk/res-auto"
	xmlns:tools="http://schemas.android.com/tools"
	android:id="@+id/myLayout"
	android:layout_width="match_parent"
	android:layout_height="match_parent"
	tools:context=".MainActivity">
<TextView
	android:id="@+id/tvAnzeige1"
	android:layout_width="317dp"
	android:layout_height="24dp"
	android:text="Anzeigefeld 1"
	app:layout_constraintBottom_toTopOf="@+id/tvAnzeige2"
	app:layout_constraintEnd_toEndOf="parent"
	app:layout_constraintStart_toStartOf="parent"
	app:layout_constraintTop_toTopOf="parent"
	app:layout_constraintVertical_bias="0.14"
	app:layout_constraintVertical_chainStyle="packed" 
/>
<TextView
	android:id="@+id/tvAnzeige2"
	android:layout_width="317dp"
	android:layout_height="24dp"
	android:text="Anzeigefeld2"
	app:layout_constraintBottom_toBottomOf="parent"
	app:layout_constraintEnd_toEndOf="parent"
	app:layout_constraintStart_toStartOf="parent"
	app:layout_constraintTop_toBottomOf="@+id/tvAnzeige1"
	app:layout_constraintVertical_bias="0.237" 
/>
</androidx.constraintlayout.widget.ConstraintLayout>
```

```java
public class MainActivity extends AppCompatActivity { 
	private ActivityMainBinding binding;
	@Override 
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.activity_main);
		binding = ActivityMainBinding.inflate(getLayoutInflater());
		View view = binding.getRoot();
		setContentView(view);
		binding.myLayout.setOnTouchListener( 
			new ConstraintLayout.OnTouchListener(){
			@Override 
			public boolean onTouch(View v, MotionEvent event) {
				handleTouch(event); 
				return true; 
			} 
		} 
	); 
}
public void handleTouch(MotionEvent event){
	binding.tvAnzeige1.setText("");
	binding.tvAnzeige2.setText("");
	int pointerCount = event.getPointerCount();
	for (int i = 0; i < pointerCount; i++) {
		int x = (int) event.getX(i);
		int y = (int) event.getY(i);
		int id = event.getPointerId(i);
		int action = event.getActionMasked();
		int actionIndex = event.getActionIndex();
		String actionString;
		switch (action) {
			case MotionEvent.ACTION_DOWN:
				actionString = "DOWN";
				break;
			case MotionEvent.ACTION_UP:
				actionString = "UP";
				break;
			case MotionEvent.ACTION_POINTER_DOWN: 
				actionString = "PNTR DOWN"; 
				break; 
			case MotionEvent.ACTION_POINTER_UP:
				actionString = "PNTR UP"; 
				break; 
			case MotionEvent.ACTION_MOVE: 
				actionString = "MOVE"; 
				break; 
			default: 
				actionString = "";
		}
		String touchStatus ="Pointer:" + i + " Action: " + actionString + "A-Index: " + actionIndex + " ID: " + id + "\n X: " + x + " Y: " + y;
		switch (i) {
			case 0: 
				binding.tvAnzeige1.setText(touchStatus); 
				break; 
			case 1:
				binding.tvAnzeige2.setText(touchStatus); 
				break;
			} 
		} 
	} 
}
```