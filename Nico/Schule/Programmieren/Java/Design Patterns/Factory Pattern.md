---
Thema:
  - "[[Java]]"
  - "[[Design Patterns]]"
---
>Nützlich wenn man dynamisch Objekte von unterschiedlichen Typen erstellen will

![[Pasted image 20260523135534.png]]
**Abstract Product**: Dient als Datentyp für die Objekte und gibt als Superklasse die konkreten Produkte vor.
**Concrete Product**: Erbt von Abstract Product und ist ein Produkt das die Factory erstellen kann.
**Factory**: Bekommt in `createProduct` z.B. als String das gewünschte Produkt übergeben, und gibt ein Objekt davon zurück.
**Client**: Das Programm das die Factory aufruft
# Beispiel
```java
abstract class AbstractProduct {
    public abstract String getType();
}

// Konkrete Produkte
class ConcreteProduct1 extends AbstractProduct {
    @Override
    public String getType() { return "Product1";}
}

class ConcreteProduct2 extends AbstractProduct {
    @Override
    public String getType() { return "Product2";}
}

// Factory
class Factory {
    public static AbstractProduct createProduct(String type) {
        if (type.equals("Product1")) {
            return new ConcreteProduct1();
        }else if (type.equals("Product2")) {
            return new ConcreteProduct2();
        }
        throw new IllegalArgumentException("Unknown Producttype: " + type);
    }
}

// Demo
public class Main {
    public static void main(String[] args) {
        AbstractProduct p1 = Factory.createProduct("Product1");
        System.out.println("Bestellt: " + p1.getType());
    }
}
```