---
Fach: "[[Programmieren]]"
tags:
Thema:
  - "[[Java]]"
---
Die **Klasse** Collections hat viele statische Methoden um mit verschiedenen [[Schule/Programmieren/Java/Basics/Datenstrukturen]] zu arbeiten.

Die Methoden verändern die übergebene Liste.
**Beispiele:**
```java
Collections.sort(zahlen); // eine Liste sortieren 
var max = Collections.max(zahlen); // größter Wert einer Collection 
System.out.println(max); // (var = Datenyp automatisch) 
Collections.shuffle(zahlen); // eine Liste zufällig mischen 
Collections.addAll(zahlen, 5, 6, 10); // mehrere Werte oder Array hinzufügen
```

| Collection                                  | Interface   | Ordered | Sorted | Thread safe | Duplicate | Nullable           |
| ------------------------------------------- | ----------- | ------- | ------ | ----------- | --------- | ------------------ |
| [[Schule/Programmieren/Java/Basics/Datenstrukturen#Array List\|ArrayList]]   | List        | Y       | _N_    | _N_         | Y         | Y                  |
| Vector                                      | List        | Y       | _N_    | Y           | Y         | Y                  |
| [[Schule/Programmieren/Java/Basics/Datenstrukturen#Linked List\|LinkedList]] | List, Deque | Y       | _N_    | _N_         | Y         | Y                  |
| CopyOnWriteArrayList                        | List        | Y       | _N_    | Y           | Y         | Y                  |
| HashSet                                     | Set         | _N_     | _N_    | _N_         | _N_       | One `null`         |
| LinkedHashSet                               | Set         | Y       | _N_    | _N_         | _N_       | One `null`         |
| [[Schule/Programmieren/Java/Basics/Datenstrukturen#Tree Set\|TreeSet]]       | Set         | Y       | Y      | _N_         | _N_       | _N_                |
| CopyOnWriteArraySet                         | Set         | Y       | _N_    | Y           | _N_       | One `null`         |
| ConcurrentSkipListSet                       | Set         | Y       | Y      | Y           | _N_       | _N_                |
| [[Schule/Programmieren/Java/Basics/Datenstrukturen#HashMap\|HashMap]]        | Map         | _N_     | _N_    | _N_         | _N (key)_ | One `null` _(key)_ |
| HashTable                                   | Map         | _N_     | _N_    | Y           | _N (key)_ | _N (key)_          |
| LinkedHashMap                               | Map         | Y       | _N_    | _N_         | _N (key)_ | One `null` _(key)_ |
| TreeMap                                     | Map         | Y       | Y      | _N_         | _N (key)_ | _N (key)_          |
| ConcurrentHashMap                           | Map         | _N_     | _N_    | Y           | _N (key)_ | _N_                |
| ConcurrentSkipListMap                       | Map         | Y       | Y      | Y           | _N (key)_ | _N_                |
| ArrayDeque                                  | Deque       | Y       | _N_    | _N_         | Y         | _N_                |
| PriorityQueue                               | Queue       | Y       | _N_    | _N_         | Y         | _N_                |
| ConcurrentLinkedQueue                       | Queue       | Y       | _N_    | Y           | Y         | _N_                |
| ConcurrentLinkedDeque                       | Deque       | Y       | _N_    | Y           | Y         | _N_                |
| ArrayBlockingQueue                          | Queue       | Y       | _N_    | Y           | Y         | _N_                |
| LinkedBlockingDeque                         | Deque       | Y       | _N_    | Y           | Y         | _N_                |
| PriorityBlockingQueue                       | Queue       | Y       | _N_    | Y           | Y         | _N_                |
