---
Fach: "[[Programmieren]]"
tags:
Thema:
  - "[[C++]]"
---
# Headerdatei
`#include <vector>`

# Initialisierung
`vector<int> v;`

# Methoden
### `.push_back()`

`v.push_back(1);` hängt dem Vector eine 1 an

### `.at()`

`v.at(0);` gibt den Wert an der ersten Stelle aus

### `.pop_back()`

`v.pop_back()` entfernt das letzte Element

### `.size()`
`v.size()` gibt die Anzahl der Elemente zurück.
Achtung: Um auf das letzte Element zuzugreifen muss `v.size()-1` verwendet werden.

### Gesamten Vector ausgeben
#### mit Zählergesteuerter Schleife:
```cpp
for(size_t i=0; i<v.size(); i++){
	cout << v.at(i) << endl;
}
```

#### mit For-Each Schleife
```cpp
for(auto i: v){
	cout << i << endl;
}
```

