---
Fach: "[[AWM]]"
Thema:
  - "[[RoomDB]]"
---
Zuerst muss in der Datei `build.gradle.kts` folgender Code in `dependencies` hinzugefügt werden:
```kts
dependencies{
	...
	val room_version = "2.2.5"
	implementation("androidx.room:room-runtime:$room_version")
	annotationProcessor("androidx.room:room-compiler:$room_version")
}
```

und für `ViewBinding`:
```kts
android{
	buildFeatures{  
	    viewBinding = true  
	}
	...
}
```
