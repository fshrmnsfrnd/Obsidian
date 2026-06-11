---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[C++]]"
---
# Zugriff auf Namespaces
### Mehrzeilig
`using namespace "<[Name des Namespace]>"`
#### Einzeilig
`namespace::command`
#### Dauerhaft einen Command bekanntmachen
`using std::cout`

# Namespace anlegen

```cpp
namespace hund{
	void gibLaut(){
		std::cout << "Wau";
	}
}
```

>Um Namespaces in eingebundenen Headerdateien zu verwenden, muss sowohl in der Header, als auch in der C++ Datei die Funktionsdefinition/deklaration in einem Namespace Block stehen (`namespace <name>{}`) 