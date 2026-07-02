---
Thema:
  - "[[C++]]"
---
# Headerdatei
---
`#include <stack>`
# Mit einem Stack arbeiten
---
**Einen Stack anlegen**
`stack<int> stapel;`

**Etwas einem Stapel hinzufügen:**
`stapel.push(42)`

**Das oberste Element eines Stapels anzeigen:**
`stapel.top()`

**Anzeigen wie viele Elemente auf einem Stapel liegen:**
`stapel.size()`

**Das oberste Element eines Stapels entfernen:**
`stapel.pop()`

**Prüfen ob etwas auf dem Stapel liegt**
`stapel.empty()`
# Codebeispiel
---
**Einen Stapel auf der Konsole anzeigen und leeren**
```cpp
while(!stapel.empty()){
	cout << stapel.top() << endl;
	stapel.pop();
}
```
