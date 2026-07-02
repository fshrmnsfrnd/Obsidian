---
Thema:
  - "[[C++]]"
---
## Funktionsdeklaration

Funktionen werden vor der Main Methode deklariert.
Die Funktionsdeklaration wird auch als Prototyp bezeichnet.

```cpp
int addiere(int a, int b);

int main(){

}
```

## Funktionsdefinition

In der Funktionsdefinition wird der eigentliche Code der Funktion geschrieben. Die Funktionsdefinition wird nach der Main Methode geschrieben.

```cpp
int addiere(int a, int b){
	int ergebnis = a + b;
	return ergebnis;
}
```

## Funktionsaufruf

Funktionen können, nachdem sie deklariert sind, von überall aufgerufen werden.

```cpp
int main(){
	summe(2, 5);
}
```


## Parameter

```cpp
int summe(int a, int b, int c = 0, int d = 0);
```
Parameter können einen Default Wert bekommen, hier `c` und `d` .
Wenn beim Funktionsaufruf keine Werte übergeben werden, werden die Default Werte verwendet.
```cpp
summe(1, 2, 3);
```
Nun haben die Parameter folgende Werte:
```cpp
a = 1
b = 2
c = 3
d = 4
```


> [!INFO] Wichtig
> Default Parameter müssen immer als letztes angegeben werden


## Referenzparameter

Mit der Syntax `int& x`  in der Funktionsdefinition wird die übergebene Variable nicht kopiert, sondern es wird auf die Variable referenziert

>Funktioniert nicht wenn die übergebene Variable im Hauptprogramm `const` ist.

### Beispiel

```cpp
void func(float &b);
int main(){
double a = 3.4;
double x = 4.7;
func(a);
//Jetzt hat a den Wert 8.1
}
void func(float& b, float& y){
	b = b + y;
	//kein return notwendig
}
```

