---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[Java]]"
---
- Der Konstruktor heißt immer genau wie die Klasse, ist `public` und hat keinen Rückgabewert.
- Ein Konstruktor kann private Variablen setzen.
- Er baut die Klasse, wenn daraus ein Objekt erzeugt wird. Ist der Konstruktor nicht eigens definiert, gibt es den Standardkonstruktor, er hat keine Übergabeparameter.
# Überladung
---
```java
public class Klasse{
	int a = 1;
	public Klasse(int a){
		this.a = a;
	}
}

public class Subklasse extends Klasse{
	int b;
	int c = 1;
	public Subklasse(int a, int b){
		super(a);
		this.b = b;
	}

	public Subklasse(int a, int b, int c){
		super(a);
		this.b = b;
		this.c = c;
	}
}
```

Jetzt können beide `Subklasse` Konstruktoren aufgerufen werden. Je nachdem wie viele Übergabeparameter übergeben werden.

```java
static void main(String[args]){
	Subklasse sk1 = new Subklasse(1, 2);
	Subklasse sk2 = new Subklasse(1, 2, 3);
}
```