---
Thema:
  - "[[Java]]"
---
Membervariablen sollen möglichst immer `private` gesetzt werden.
Soll auf die Variablen zugegriffen werden, werden Getter und Setter verwendet

```java
public Bierfass(double fuellstand) { 
	this.fuellstand=fuellstand; 
	sorte="Edelstoff"; 
} 

public void setSorte(string sorte) { 
	this.sorte = sorte 
}
```