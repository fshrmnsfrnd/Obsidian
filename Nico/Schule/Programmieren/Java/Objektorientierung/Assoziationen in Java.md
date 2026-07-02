---
Thema:
  - "[[Java]]"
---
# Einfache Assoziationen
---
![[UML Klassendiagramm#Einfache Assoziationen]]
## Umsetzung
```java
public class Stadion {
	private Fan fan1; 
	private Fan fan2; 
	
	public Stadion(Fan fan1, Fan fan2) { 
		this.fan1 = fan1; 
		this.fan2 = fan2; 
	}  
}

Fan fan1 = new Fan();
Fan fan2 = new Fan();
Stadion stadion1 = new Stadion(fan1, fan2);
```
Die [[Objekte in Java]] werden in Main erzeugt und das zu lesende Objekt wird dem lesenden Objekt übergeben
# Multiplizitäten
---
![[UML Klassendiagramm#Multiplizitäten]]
# Aggregation
---
![[UML Klassendiagramm#Aggregation]]
## Umsetzung
```java
Fan fan1 = new fan();
Station station1 = new Stadion();
stadion1.add(fan1);
```
Die Objekte werden in Main erzeugt und das zu lesende Objekt wird dem lesenden Objekt übergeben
# Komposition
---
![[UML Klassendiagramm#Komposition]]
## Umsetzung
```java
public class Haus{
	private Raum raum1;
	public Haus(){
		raum1 = new Raum()
	}
}
```
Die Einzelteile werden im [[Konstruktor]] erzeugt
# Rollen
---
![[UML Klassendiagramm#Rollen]]
