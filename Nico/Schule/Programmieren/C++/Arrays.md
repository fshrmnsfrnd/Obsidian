---
Thema:
  - "[[C++]]"
---
>Ein **Array** ist eine Sammlung von Elementen **gleichen Typs** mit **fester Größe**, fortlaufend im
>Speicher abgelegt.
# Deklaration & Initialisierung
---
```cpp
int a1[5];                    // 5 Elemente, uninitialisiert
int a2[5] = {1, 2, 3, 4, 5};  // mit Werten
int a3[]  = {1, 2, 3};        // Größe automatisch -> 3
int a4[5] = {1, 2};           // Rest wird mit 0 gefüllt
int a5[5] = {};               // alle Elemente 0
```
# Zugriff
---
Index ist ==0-basiert==, das erste Element hat Index `0`, das letzte `Länge-1`.
```cpp
int a[3] = {10, 20, 30};
cout << a[0];   // 10
a[2] = 99;      // letztes Element überschreiben
```
> [!WARNING] Kein Bounds-Checking
> C++ prüft die Array-Grenzen **nicht**. `a[5]` bei `int a[3]` lässt sich kompilieren, führt aber zu undefiniertem Verhalten.
# Größe bestimmen
---
Die Anzahl der Elemente ergibt sich aus der Gesamtgröße geteilt durch die Größe eines Elements.
```cpp
int a[5];
size_t n = sizeof(a) / sizeof(a[0]);  // 5
```
> [!NOTE] std::size (ab C++17)
> Mit `#include <iterator>` liefert `std::size(a)` die Länge direkt und sicherer als `sizeof`.
# Durchlaufen
---
## Zählergesteuerte Schleife
```cpp
for(size_t i = 0; i < n; i++){
    cout << a[i] << endl;
}
```
## Range-based for (For-Each)
```cpp
for(int x : a){
    cout << x << endl;
}
```
# Mehrdimensionale Arrays
---
```cpp
int matrix[2][3] = { {1, 2, 3}, {4, 5, 6} };
int x = matrix[1][0];   // 4
for(size_t i = 0; i < 2; i++){
    for(size_t j = 0; j < 3; j++){
        cout << matrix[i][j] << " ";
    }
}
```
# Arrays & Funktionen
---
Beim Übergeben "zerfällt" ein Array zu einem Zeiger (**Array Decay**), wodurch die Größeninformation verloren geht und separat übergeben werden muss.
```cpp
void print(int arr[], size_t n){
    for(size_t i = 0; i < n; i++) cout << arr[i] << " ";
}
print(a, n);
```
# Array vs. std::vector
---
Faustregel: feste, zur Compilezeit bekannte Größe -> Array, sonst dynamisch wachsend -> [[Vectors in C++|vector]].

| Eigenschaft    | Array                  | `vector`                |
| -------------- | ---------------------- | ----------------------- |
| Größe          | fest (Compilezeit)     | dynamisch (Laufzeit)    |
| Header         | keiner nötig           | `#include <vector>`     |
| Länge abfragen | `sizeof` / `std::size` | `.size()`               |
| Bounds-Check   | nein                   | `.at()` wirft Exception |

