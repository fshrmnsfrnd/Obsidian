---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[Java]]"
---
Der Hauptgrund für abstrakte [[Klassen in Java|Klassen in Java]] ist, dass von ihnen kein Objekt erzeugt werden kann. Sie dienen als Superklassen für andere Klassen.
# Abstrakte Klasse definieren
---
```java
public abstract class Klasse{}
```
# Abstrakte Klassen verwenden
---
```java
public class SubKlasse extends Klasse{}
```
# Abstrakte Methoden
---
Ist eine Methode abstrakt muss diese in der Subklasse definiert werden.
```java
abstract class Klasse{
    public void methode1(){
        System.out.println("Methode 1");
    }

    public abstract void methode2();
}

class SubKlasse extends Klasse{
    @Override
    public void methode2() {
        System.out.println("Methode 2 SubKlasse");
    }
}

public class Main {
    public static void main(String[] args) {
        Klasse o1 = new SubKlasse();
        o1.methode1(); //Methode 1
        o1.methode2(); //Methode 2 SubKlasse
    }
}
```

Ist eine Methode nicht abstrakt, muss sie auch nicht überschrieben werden. 
Ist eine Methode abstrakt muss die ganze Klasse abstrakt sein.