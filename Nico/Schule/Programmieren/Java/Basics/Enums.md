---
Fach: "[[Programmieren]]"
tags:
Thema:
  - "[[Java]]"
---
Enums sind basicly normale Klassen mit Attributen und Methoden. Statt einem Konstruktor hat man vorher festgelegte Kombinationen von Startwerten (Enum Konstanten) hier z.B. ESCHE. Jede Enum Konstante kann auch als Objekt verwendet werden mit `Enum.Konstante` 
# Erstellen
---
```java
public enum TreeType {
    BERGAHORN("Bergahorn",-0.62466,0.73312,-0.00482),
    DOUGLASIE("Douglasie",-2.13785,0.91597,-0.00375),
    ESCHE("Esche",-7.97623,1.40182,-0.01011);

    private final String name;
    public final double A;
    public final double B;
    public final double C;

    TreeType(String name, double A, double B, double C){
        this.name = name;
        this.A = A;
        this.B = B;
        this.C = C;
    }
    
    public String getName(){
        return this.name;
    }
}
```

> [!NOTE] Konstruktoren sind immer `private` daher kann es weggelassen werden
> Es kann mehrere Konstruktoren geben
# Verwenden
---
```java
TreeType treeType = TreeType.DOUGLASIE;
treeType == TreeType.DOUGLASIE; //true
treeType.getName(); //Douglasie
TreeType.ESCHE.getName(); //Esche
```