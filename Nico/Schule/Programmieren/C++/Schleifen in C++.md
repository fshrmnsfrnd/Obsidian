---
Thema:
  - "[[C++]]"
---
## Zählergesteuert

```cpp
for(int i = 1; i <= 10; i++){
	cout << i << ' ';
}
```
 Ausgabe:
 `1 2 3 4 5 6 7 8 9 10`

## For-each Schleife

```cpp
for(auto i: vs){
	cout << i;
}
```

Greift auf jedes Element aus `vs` zu. Das Element ist in der Schleife über i aufrufbar. VS kann z.B. ein [[Vectors in C++]], [[Schule/Programmieren/C++/Arrays]] oder [[Strings in C++]] sein.

## Kopfgesteuert

```cpp
int i = 1;
while(i <= 10){
	cout << i << ' ';
	i++;
}
```
Ausgabe:
 `1 2 3 4 5 6 7 8 9 10`


> [!NOTE] Einzeilige Schleifen
> Wenn die Schleife nur eine einzelne Zeile Code enthält, können die geschweiften Klammern weggelassen werden
```cpp
for (i = 1; i < 10; i++)
	cout << i << " ";
```


## Fußgesteuert

>Wird mindestens 1 Mal ausgeführt

```cpp
int i = 1;
do{
	cout << i << ' ';
	i++;
}while(i <= 10);
```
Ausgabe:
 `1 2 3 4 5 6 7 8 9 10`

## Bedingungen

Als Bedingungen in den runden Klammern "()" werden Bedingungen angegeben
Hier können [[Mathematische Ausdrücke#Vergleich|Vergleiche]] verwendet werden.
Es gibt auch den "Nicht" Operator:
```cpp
while(!stapel.empty()){
	cout << stapel.top() << endl;
	stapel.pop();
}
```
Solange im Stapel noch etwas liegt gibt `stapel.empty()` `false` zurück.
Die Schleife soll aber ausgeführt werden, solange `false` zurückgegeben wird.
Hierfür wird ein '!' vor die Bedingung geschrieben