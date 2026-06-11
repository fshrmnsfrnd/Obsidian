---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
Toasts sind Popup Fenster die eine einfache Meldung anzeigen

# Erzeugen und Anzeigen
---
**Ausführlich:**
```java
Context context = getApplicationContext(); 
String text = "Hello World!";
int duration = Toast.LENGTH_SHORT;
Toast toast = Toast.makeText(context, text, duration); 
toast.show();
```
 **Kurz:**
 ```java
 Toast.makeText(getApplicationContext(), "Hello World!", Toast.LENGTH_SHORT).show();
 ```

