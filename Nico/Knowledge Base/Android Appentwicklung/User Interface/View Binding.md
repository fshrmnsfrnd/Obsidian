---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
>Bindings ermöglichen die Interaktion zwischen Code und den [[Views|Views]]


> [!WARNING] View Binding oder Find View By Id?
> Google empfiehlt die Verwendung von View-Binding wo immer möglich. Möglicherweise wird die Find View By Id - Variante in einer der zukünftigen Version von Android Studio entfernt werden.

## Binding aktivieren
In `build.gradle.kts` unter Gradle Scripts mit Module `app`:
```java
...
android{
	buildFeatures{
		viewBinding = true
	}
	...
}
...
```
**Synchronisieren mit Sync now.**

## Binding verwenden
In der MainActivity muss folgendes gemacht werden
```java
...
import de.ts.btin2.databinding.ActivityMainBinding; 
... 

public class MainActivity extends AppCompatActivity { 
	private ActivityMainBinding binding;
	TextView sampleElement;
	
	@Override 
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState); 
		//Binding
		binding = ActivityMainBinding.inflate(getLayoutInflater()); 
		setContentView(binding.getRoot());
	} 
	... 
	sampleElement.setText("Hi");
	binding.exampleView.setText("Hallo");
}
```


# FindViewById (deprecated)
---

> [!WARNING] NICHT verwenden! (Außer Lingo will es explizit)

>Alle Ressourcen, aus denen eine Anwendung besteht, werden in einer Klasse namens **R** zusammengefasst. Die Klasse R enthält die Unterklasse **Layout**, die die Layout-Ressourcen und die [[Views|Views]] beinhaltet.

`onCreate()` überschreiben, dann kann überall auf `findViewById(R.id.<idOfView>)` zugegriffen werden
```java
public class MainActivity extends AppCompatActivity { 
	@Override 
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState); 
		setContentView(R.layout.activity_main);  //nur für findViewById()
	} 
	... 
	TextView exampleView = findViewById(R.id.exampleView);
	exampleView.setText("Hallo");
}
```

