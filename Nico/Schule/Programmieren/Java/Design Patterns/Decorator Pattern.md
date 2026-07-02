---
Thema:
  - "[[Design Patterns]]"
  - "[[Java]]"
---
![[Pasted image 20260305102605.png|697]]
**Component**: Definiert ein Interface, basically damit man einen Datentyp für die Ganzen anderen Klassen hat.
**ConcreteComponent**: Ein reiner Component, von dem es am Ende nur **einen** gibt und der in beliebig viele Decorators eingepackt sein kann.
**Decorator**: Eine abstrakte Klasse, die ein Component Objekt hält (Das 1 Objekt oder einen weiteren Decorator) und verschiedene Methoden, je nach anwendungsfall. Die hier implementierte Decorator Methode führt immer die selbe Methode des gespeicherten Components aus.
**ConcreteDecorator**: Ein Decorator, der in seinen Methoden `super.method()` aufruft, und anschießend seinen Decorator Zweck ausführt.

# Beispiel für das ganze "Methode des inneren Objekts aufrufen" Ding
---
![[Pasted image 20260305104335.png]]

# Code Beispiel
---
**Component:**
```java
public interface Car {  
    void upgrade();  
}
```

**Concrete Component**
```java
public class Acura implements Car{  
    @Override  
    public void upgrade() {  
        System.out.println("Acura Base Model");  
    }  
}
```

**Concrete Component**
```java
public class BMW implements Car{  
	  
    @Override  
    public void upgrade() {  
        System.out.println("BMW Base Model");  
    }  
}
```

**Decorator**
```java
public abstract class CarDecorator implements Car{  
    private Car car;  
	  
    public CarDecorator(Car car) {  
        this.car = car;  
    }  
	  
    public void upgrade(){  
        this.car.upgrade();  
    };  
}
```

**Concrete Decorator**
```java
public class CarNavigationDecorator extends CarDecorator{  
	
	public CarNavigationDecorator(Car car) {  
		super(car);  
	}  
	
	@Override  
	public void upgrade(){  
		super.upgrade();  
		System.out.println("Navi");  
	}  
}
```

**Concrete Decorator**
```java
public class CarTireDecorator extends CarDecorator{  
	  
    public CarTireDecorator(Car car) {  
        super(car);  
    }  
	  
    @Override  
    public void upgrade(){  
        super.upgrade();  
        System.out.println("Alufelgen");  
    }  
}
```

**Main**
```java
public class Main {  
    public static void main(String[] args) {  
        Car full = new CarNavigationDecorator(new CarTireDecorator(new BMW()));  
        full.upgrade();  
    }  
}
```
