---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
>Objekte der Klasse Drawable werden mit dem [[Image View]] Steuerelement angezeigt. Das ImageView übernimmt dabei die Arbeit das Drawable-Objekt zu laden und zu skalieren.

# Drawables zum Projekt hinzufügen
---
Grafiken und Bilder werden im Order `res/drawable` eingefügt. Empfohlen ist das Format `.png`

Um im Code auf die Ressourcen zuzugreifen wird die Ressource-ID (Name der Datei ohne Endung) verwendet.

# Drawables in Layout verwenden
---
Am besten mit einem Steuerelement `ImageView` der `activity.xml` hinzufügen.

in der `activity_main.xml` sieht das dann so aus:
```xml
<ImageView
 android:id="@+id/imgMebis"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:layout_marginTop="32dp"
 app:layout_constraintEnd_toEndOf="parent"
 app:layout_constraintStart_toStartOf="parent"
 app:layout_constraintTop_toTopOf="parent"
 app:srcCompat="@drawable/mebis1" />
```
Die Ressource wird hierbei mit der Zeile `app:srcCompat="@drawable/mebis1"` zugewiesen.

# Transitions
---
## Statische Transition
Um eine Transition zwischen 2 Bildern zu erstellen, wird in `res/drawables` eine neues Drawable Resource File mit `Root Element: transition` erstellt (Rechtsklickmenü).

Inhalt in der Datei erstellen:
```xml
<transition xmlns:android="http://schemas.android.com/apk/res/android">
	<item android:drawable="@drawable/bild1"/>
	<item android:drawable="@drawable/bild2"/>
</transition>
```

Die Transition im Code verwenden:
```java
public void startTransition(View view){ 
	Resources res = view.getContext().getResources(); 
	TransitionDrawable transition; 
	//Transition erzeugen 
	transition = (TransitionDrawable) ResourcesCompat.getDrawable(res,
		R.drawable.img_transition_1, null); 
	//Transition an ImageView übergeben 
	myImageView.setImageDrawable(transition); 
	//Transition starten 
	transition.startTransition(3000); 
}
```

## Dynamische Transition
```java
public void startTransition(View view){ 
	Resources res = view.getContext().getResources(); 
	TransitionDrawable transition = new TransitionDrawable(new Drawable[]{
		R.drawables.newImg, R.drawables.oldImg
	});
	//Transition an ImageView übergeben 
	myImageView.setImageDrawable(transition); 
	//Transition starten 
	transition.startTransition(3000); 
}
```