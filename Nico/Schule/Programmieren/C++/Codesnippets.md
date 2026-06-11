---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[C++]]"
---
## Header

```cpp
#include <iostream> //cout und cin
#include <iomanip> //Ausgabeformatierung
#include <stack> //Stack
#include <cmath> //Mathematische Funktionen
#define <_USE_MATH_DEFINES> //Mathematische Werte
#include <ctime> //Zeit für random Zahlen

using namespace std;
```


## IF

```cpp
if(<true>){
	//Code
}else if(<true>){
	//Code
}else{
	//Code
}
```

## Funktion

```cpp
//definition
int func(int a, char& b, double c = 1.1);

int main(){
	int x = 1;
	char y = 'A';
	func()
}

int func(int a, char& b, double c = 1.1){
	b = a + c;
	c = a + b;
	return c;
}
```


## [[Stacks in C++]] ausgeben und leeren

```cpp
while(!stapel.empty()){
	cout << stapel.top() << endl;
	stapel.pop();
}
```

## Zwei Variablen tauschen

```cpp
//Datentyp muss angepasst werden
void tauschen(int& a, int&b){
	int temp;
	temp = a;
	a = b;
	b = temp;
}
```


## 3 Werte sortieren und Counter zurückgeben

```cpp
unsigned int sortiere(float& x, float& y, float& z){
	float hilf;
	int counter = 0;
	do{
		if(x > y){
			hilf = x;
			x = y;
			y = hilf;
			counter++;
		}
		if(y > z){
			hilf = y;
			y = z;
			z = hilf;
			counter++;
		}
	}while(x > y || y > z);

	return counter;
}
```

## Fakultät berechnen

```cpp
//Datentyp anpassen
int faculty(unsigned int number){
	unsigned int faculty = 1;
	if(number > 0){
		for(number; number > 0; --number){
			faculty = faculty * number;
		}
	}
	return faculty;
}
```

## Brutto berechnen

```cpp
double bruttoberechnen(unsigned int steuersatz, unsigned int nettobetrag) {
	return nettobetrag * (1 + (steuersatz / 100.0));
}
```

## Quadratische Funktion berechnen

```cpp
double quadfunc(double a, double b, double c, double x) {
	double y = a * (x * x) + b * x + c;
	return y;
}
```

## Ist Schaltjahr


```cpp
bool isschaltjahr(int jahreszahl) {
	bool istschaltjahr;
	if(jahreszahl % 4 == 0){
		istschaltjahr = true;
		if(jahreszahl % 100 == 0){
			istschaltjahr = false;
			if(jahreszahl % 400 == 0){
				istschaltjahr = true;
			}
		}
	}
	return istschaltjahr;
}
```

## [[Zufallszahlen]]

Headerdatei: 
`#include <ctime>`

Funktion Initialisieren:
`srand((unsigned) time(nullptr))`

Zufallszahl erzeugen:
`rand()`

#### Wertebereich definieren

`i = rand() % 100 + 1`
$[1; 100]$ 

`i = rand() % 101`
$[0; 100]$ 

`i = rand() % 51 + 50`
$[50; 100]$ 

`i = rand() % 199 - 99`
$[-99; 99]$ 

`i = rand() % 21 (*0.5) / 2.0`
$[0; 0,5; 1; ... ; 9,5; 10]$ 

##### Funktion für [[Zufallszahlen]]

```cpp
#include <ctime>
double randNum(int min, int max, double schrittweite = 1.0) {
	srand((unsigned)time(nullptr));
	int range = max - min;
	double devisor = 1.0 / schrittweite;
	double k = rand() % range + min / devisor;
	return k;
}
```