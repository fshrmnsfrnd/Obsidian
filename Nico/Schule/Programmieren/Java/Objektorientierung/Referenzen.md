---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[Java]]"
---
Bei Objekten (z.B. String) werden in Java Referenzen übergeben.
Einfache Datentypen (z.B. int, char) werden als Kopie übergeben.

>Variablen mit eine Klasse als Typ sind immer Referenzen. Eine Variable kann nicht speziell als Referenz gekennzeichnet werden

```java
Object a = "5";
Object b = a;
b = "6";
System.out.println(a);//Gibt 6 aus
```


![[Pasted image 20250508092728.png]]
Dies ist aber nur für Theorie relevant, nicht für das eigentliche programmieren, da man durch `wagen2 = "NE-BJ69"` nicht `wagen1` verändert
# Garbage Collector
Der Garbage Collector kontrolliert regelmäßig den Arbeitsspeicher, und gibt den Speicherplatz von Objekten frei, auf die keine Referenz zeigt.

# Hüll- oder Wrapperklassen
Wrapperklassen sind [[Klassen in Java|Klassen in Java]] wie `Integer` die Funktionen für den jeweiligen einfachen Datentypen bereitstellen.
Durch **Autoboxing** werden Wrapperklassen und einfache Datentypen automatisch ineinander umgewandelt.

