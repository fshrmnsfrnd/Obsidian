---
Thema:
  - "[[Java]]"
  - "[[Design Patterns]]"
---
>Der Sinn ist `.clone()` statt `new` zu verwenden, weil es performanter ist, und die initialen Objekte nie verändert werden.

---
![[Pasted image 20260319082832.png]]

---
**Mit Prototype Manager**
Der `PrototypeManager` erstellt beim Programmstart von jedem `ConcretePrototype` ein Objekt, und gibt denen eine ID. Will man dann z.B. ein `ConcretePrototypeA` Objekt, macht man `PrototypeManager.getObjectOfType('CPA')`, dann returned der `PrototypeManager` ein geklontes Objekt vom originalen `ConcretePrototypeA`.

---
Geht auch ohne `PrototypeManager` zwischen `Client` und den `ConcretePrototypes`, taugt dann aber nix
Die `Prototype` Klasse ist dafür da um eine Map mit dem Datentypen `Prototype` im `PrototypeManager` zu halten.

---
# Beispiel
---
`Prototype`
```java
public abstract class ProductPrototype implements Cloneable{
	private String name;
	private Long produkt_nummer;
	
	@Override
	public ProductPrototype clone(){
		ProductPrototype clone = null;
		try{
			clone = (ProductPrototype) super.clone();
		}
		catch(CloneNotSupportedException e){
			e.printStackTrace();
		}
		return clone;
	}
	
	public Long getProdukt_nummer() {
		return produkt_nummer;
	}
	
	public void setProdukt_nummer(Long produkt_nummer) {
		this.produkt_nummer = produkt_nummer;
	}
	
	public String getName() {
		return name;
	}
	
	public void setName(String name) {
		this.name = name;
	}
}
```
---
`PrototypeManager`
```java
enum VALID_PRODUCTS{
    CD,
    DVD,
    BUCH
}

public class PrototypeManager {
    HashMap<VALID_PRODUCTS, ProductPrototype> prototypeHashMap = new HashMap<>();
  
    public PrototypeManager(){
        prototypeHashMap.put(VALID_PRODUCTS.BUCH, new Buch());
        prototypeHashMap.put(VALID_PRODUCTS.CD, new CD());
        prototypeHashMap.put(VALID_PRODUCTS.DVD, new DvD());
    }
  
    public ProductPrototype getPrototype(VALID_PRODUCTS product){
        return prototypeHashMap.get(product).clone();
    }
}
```
---
`DvD`
```java
public class DvD extends ProductPrototype{}
```

`CD`
```java
public class CD extends ProductPrototype{}
```

`Buch`
```java
public class Buch extends ProductPrototype{}
```
