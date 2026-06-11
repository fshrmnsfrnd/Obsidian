---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[C++]]"
---
```cpp
switch(variable){
	case 1:
		cout << "Case 1\n"
		break;
	case 2:
		cout << "Case 2\n";
	case 3:
		cout << "Case 3\n";
		break;
	default:
		cout << "Default\n"
}
```

#### Output für `Variable = 1`:
Case 1

#### Output für `Variable = 2`:
Case 2
Case 3

#### Output für `Variable = 10`:
Default