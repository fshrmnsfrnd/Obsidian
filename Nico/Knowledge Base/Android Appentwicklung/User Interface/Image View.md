---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
>Mit einem ImageView können [[Drawable|Drawables]] geladen, angezeigt und skaliert werden.

```java
public class MainActivity extends AppCompatActivity { 
	ImageView imgView; 
	int imageNumber = 1;
	
	@Override 
	protected void onCreate(Bundle savedInstanceState) { 
		super.onCreate(savedInstanceState); 
		//Find View By Id
		setContentView(R.layout.activity_main); 
		imgView = (ImageView) findViewById(R.id.imgView); 
		//Besser: Binding
		binding = ActivityMainBinding.inflate(getLayoutInflater());
		setContentView(binding.getRoot);
		imgView = binding.imgView;
	}	
}
```
# Bilder dynamisch verändern
---
**Durchklicken mit Switch Case:**
`MainActivity.java`
```java
public class MainActivity extends AppCompatActivity { 
	...
	public void changeImage(View view) {
		Resources res = view.getContext().getResources(); 
		Drawable img = null; 
		switch (imageNumber){ 
			case 1: 
				img = ResourcesCompat.getDrawable(res, R.drawable.img2, null);
				imageNumber = 2;
				break;
			case 2:
				default: 
					img = ResourcesCompat.getDrawable(res, R.drawable.img1, null);
					imageNumber = 1;
		}
		imgView.setImageDrawable(img);
	}
}
```

**Bestimmtes Bild anzeigen (Beispiel mit [[Spinner]]):**
```java
public class MainActivity extends AppCompatActivity { 
	...
	@Override  
	public void onItemSelected(AdapterView<?> parent, View view, int position, long id)
	{  
	    selected = parent.getItemAtPosition(position).toString();  
	    int resId = getResources().getIdentifier(
		    selected.toLowerCase(),
		    "drawable", getPackageName()
		);  
	    imgView.setImageResource(resId);  
	}
}
```