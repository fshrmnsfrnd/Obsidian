---
Thema:
  - "[[Java]]"
---
> Vererbung beschreibt das Konzept, dass Attribute und Methoden an andere Klassen weitergegeben werden können

Möglichkeiten sind:
- [[Klassen in Java]]
- [[Interfaces]]
- [[Abstrakte Klassen]] 
# Beispiel
---
```java
public class Superclass{
    private int attribute1;
    public int attribute2 = 2;
    public Superclass(int attribute1) {
        this.attribute1 = attribute1;
    }
    public int getAttribute1(){return attribute1;}
    public String getName(){return "Superclass";}
}

public class Subclass extends Superclass{
    //Zusätzliches Attribut
    public int attribute3;
    //Konstruktor
    public Subclass(){
        //Als erstes Konstruktor der Oberklasse aufrufen
        super(1);
        //Dann eigenes machen
        this.attribute3 = 3;
    }
    //Eigene zusätzliche Methode
    public int getAttribute2(){return super.attribute2;}
    //Methode der Oberklasse überschreiben
    public String getName(){return "Subclass";}
}

void main() {
    Subclass o1 = new Subclass();
    o1.getAttribute1(); //1
    //o1.attribute2; //Gibt es nicht
    o1.getAttribute2(); //2
    o1.getName(); //Subclass
    
    Superclass o2 = new Subclass();
    //o2.getAttribute2(); //Gibt es nicht
    o2.getName(); //Subclass
}
```
