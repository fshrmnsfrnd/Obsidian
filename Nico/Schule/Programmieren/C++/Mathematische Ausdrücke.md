---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[C++]]"
---
## Mathematische Werte

**Headerdatei:**
`#define <_USE_MATH_DEFINES>`

**Variablen:**

| Mathematisch | C++ Variable |
| ------------ | ------------ |
| $\pi$        | M_PI         |


## Arithmetische Ausdrücke

| arithmetische Operation              | mathematische Schreibweise | C++ Schreibweise |
| ------------------------------------ | -------------------------- | ---------------- |
| Addition                             | a + b                      | a + b            |
| Subtraktion                          | a - b                      | a - b            |
| Multiplikation                       | a • b                      | a * b            |
| Division mit Gleitkommazahlen        | a : b                      | a / b            |
| Ganzzahldivision ohne Rest           | a                          | a / b            |
| Rest einer Ganzzahldivision (Modulo) |                            | a % b            |

## Mathematische Funktionen

Alle anderen mathematischen Funktionen werden als Funktion aufgerufen.
Hierfür muss die Headerdatei `cmath` eingebunden sein.
`#include <cmath>`

| Funktion                | mathematische Schreibweise | C++-Schreibweise |
| ----------------------- | -------------------------- | ---------------- |
| Potenzieren             | $a^b$                      | pow( a , b)      |
| Wurzelziehen            | √a                         | sqrt( a )        |
| Sinus                   | sin a                      | sin( a )         |
| Kosinus                 | cos a                      | cos( a )         |
| nat. Logarithmus        | ln a                       | log( a )         |
| e-Funktion              | $e^a$                      | exp( a )         |
| Arcus-Tangens           | arctan (x)                 | atan( x )        |
| Betrag (int-Wert)       | \|a\|                      | abs( a )         |
| Betrag (float-Wert)     | \|a\|                      | fabs( a )        |
| Abrunden auf ganze Zahl | ⎣a⎦                        | floor(a)         |

## Inkrement und Dekrement

| ++x | x wird um den Wert 1 erhöht, bevor x im Ausdruck weiterverwendet wird.     |
| --- | -------------------------------------------------------------------------- |
| --x | x wird um den Wert 1 erniedrigt, bevor x im Ausdruck weiterverwendet wird. |
| x++ | x wird inkrementiert, nachdem x im Ausdruck verwendet wurde.               |
| x-- | x wird dekrementiert, nachdem es im Ausdruck verwendet wurde.              |
**Beispiel:**

```cpp
/* Variablendefinitionen */ 
int i=1, j=1; 
/* Anweisungen */ 
cout << i++ << endl; // Ausgabe 1, neuer Wert von i ist 2
cout << ++j << endl; // Ausgabe 2, neuer Wert von j ist 2
```

## Vergleich

| Vergleich               | C++ Schreibweise |
| ----------------------- | ---------------- |
| a gleich b              | a == b           |
| a größer b              | a > b            |
| a kleiner b             | a < b            |
| a größer oder gleich b  | a >= b           |
| a kleiner oder gleich b | a <= b           |
| a ungleich b            | a != b           |
