---
Thema:
  - "[[Java]]"
---
Man kann die Container-Klassen grob den folgenden Kategorien zuordnen: 
- **Listen** (Interface `List<E>`) 
	- Speichern ihre Elemente der Reihe nach entweder in einem Array oder als sogenannte verkettete Liste, bei der jedes Objekt seinen Nachfolger und vielleicht auch seinen Vorgänger kennt. 
- **Mengen** (Interface `Set<E>`) 
	- Enthalten keine doppelten Elemente
- **Assoziativspeicher** (Interface `Map<K, V>`) 
	- Ordnen einem Schlüssel K (**key**) einem Wert V (**value**) zu. 
- **Schlangen** (Interface `Queue<E>`) 
	- Sind hauptsächlich dafür gedacht, Objekte am Ende hinzuzufügen und am Anfang wegzunehmen

# Linked List
---
```java
LinkedList<E> l = new LinkedList<>();
```
In einer Linked List ist jedes Element ein `Value` und eine Referenz auf das nächste Objekt.
Man kann nicht über einen Index darauf zugreifen.
Um Daten einzufügen muss aber nur eine Referenz geändert werden.
Es gibt ein eigenes `Tail` und ein `First` Objekt.
## Methoden
---

| Methode                            | Beschreibung                |
| ---------------------------------- | --------------------------- |
| `add([int index,] <E> element)`    | Fügt ein Element an/ein     |
| `addFirst(<E> element)`            | fügt vorne ein Element an   |
| `addLast(<E> element)`             | fügt hinten ein Element an  |
| `get(int index)`                   |                             |
| `getFirst()`                       |                             |
| `getLast()`                        |                             |
| `contains(<E> element)`            |                             |
| `indexOf(<E> element)`             |                             |
| `remove({<E> element\|int index})` |                             |
| `isEmpty()`                        |                             |
| `pop()`                            | Entfernt das letzte Element |
| `push(<E> element)`                | Fügt am Ende ein Objekt an  |
| `size()`                           |                             |
# Array List
---
```java
ArrayList<E> a = new ArrayList<>();
```
Eine Array List ist im Hintergrund eine normales Array.
Es kann per Index auf die Elemente zugegriffen werden.
Wenn ein Element eingefügt wird muss aber das gesamte Array kopiert werden.
## Methoden
| Methode                            | Beschreibung                |
| ---------------------------------- | --------------------------- |
| `add([int index,] <E> element)`    | Fügt ein Element an/ein     |
| `addFirst(<E> element)`            | fügt vorne ein Element an   |
| `addLast(<E> element)`             | fügt hinten ein Element an  |
| `get(int index)`                   |                             |
| `getFirst()`                       |                             |
| `getLast()`                        |                             |
| `contains(<E> element)`            |                             |
| `indexOf(<E> element)`             |                             |
| `remove({<E> element\|int index})` |                             |
| `isEmpty()`                        |                             |
| `pop()`                            | Entfernt das letzte Element |
| `push(<E> element)`                | Fügt am Ende ein Objekt an  |
| `size()`                           |                             |
# Tree Set
---
```java
TreeSet<E> t = new TreeSet<>();
```
Das ist ein balancierter [[B Trees|Binärbaum]]. Jedes Element hat ein Child das größer ist und eins das kleiner ist.
Das erste Element das eingefügt wird ist die Wurzel.
Wenn ein neues Element hinzugefügt wird wird der Baum neu aufgebaut um die Balance zu halten.
Balance bedeutet, dass alle Zweige +-1 gleich lang sind.
# HashMap
---
```java
HashMap<E, W> h = new HashMap<>();
```
Eine HashMap ist ein Key <-> Value Store.
## Methoden

| Methode                                    | Beschreibung                 |
| ------------------------------------------ | ---------------------------- |
| `put(<key>, <value>)`                      | fügt Daten hinzu             |
| `get(<key>)`                               | gibt den Value zurück        |
| `isEmpty()`                                |                              |
| `size()`                                   |                              |
| `keySet()`                                 | returns a List of the Keys   |
| `values()`                                 | returns a List of the Values |
| `replace(<key>, [<oldValue>,] <newValue>)` |                              |
| `remove(<key>, [, <value>])`               |                              |
### Beim initialisieren deklarieren
**Beispiel**
```java
HashMap<String, HashMap<Character, Double>> BaumKoffizienten= new HashMap<>() {  
    {  
        put("Fichte", new HashMap<>(){  
            {  
            put('A' , 0.85149);  
            put('B', 0.60934);  
            put('C', -0.00228);  
            }  
        });  
  
        put("Tanne", new HashMap<>(){  
            {  
                put('A' , 1.76896);  
                put('B', 0.59175);  
                put('C', 0.0);  
            }  
        }); 
    }  
};
```
# Iterator
---
Die Klasse Iterator ist ein Hilfsmittel, um mit dem selben Code die Elemente verschiedener Datenstrukturen zu durchlaufen, die das Interface Collection implementieren.
```java
LinkedList<Integer> list = new LinkedList<>();
list.add(1);
list.add(2);
list.add(3);

Iterator<Integer> iterator = list.iterator();
Iterator<Integer> iterator1 = list.descendingIterator();

while (iterator.hasNext()) {
	Object next = iterator.next();
	System.out.println(next);
}
```
# Sonstige Container
---
- Map (Key Value)
- HashSet (Key Value)
- ...