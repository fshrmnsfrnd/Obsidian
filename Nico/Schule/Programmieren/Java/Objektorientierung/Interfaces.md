---
Fach: "[[Programmieren]]"
tags:
Thema:
  - "[[Java]]"
---
Ein Interface ist wie eine [[Abstrakte Klassen|Abstrakte Klasse]], die keine Attribute hat, und ausschließlich abstrakte Methoden hat. Ein Interface kann Konstanten haben. Von einem Interface können keine [[Objekte in Java]] erzeugt werden.

Eine Klasse kann mehrere Interfaces verwenden.

Interfaces sind der einzige Weg für Mehrfachvererbung in Java.

In Interfaces können keine Variablen deklariert werden, sie müssen auch definiert werden

# Interfaces definieren
---
```java
interface Inter{
    public void method1();
    public default void  method2(){
        System.out.println("Method 2");
    }
}
```

# Interfaces verwenden
---
```java
class Klasse implements Inter{
    public void method1() {
        System.out.println("Methode 1");
    }

    public void method3() {
        System.out.println("Methode 3 Subklasse");
    }
}
```
Alle Methoden des Interfaces müssen implementiert werden, es ist kein `@Override` und kein `abstract` nötig, kann der Lesbarkeit halber aber verwendet werden.
# Beispiel
---
```java
public class Main {
    public static void main(String[] args) {
        Inter o1 = new Klasse();
        o1.method1(); //Methode 1
        o1.method2(); //Methode 2
        //o1.method3(); //Gibt es nicht
        Klasse o2 = new Klasse();
        o2.method1(); //Methode 1
        o2.method2(); //Methode 2
        o2.method3(); //Methode 3 Subklasse
    }
}
```