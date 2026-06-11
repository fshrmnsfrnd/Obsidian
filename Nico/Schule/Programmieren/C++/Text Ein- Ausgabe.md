---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[C++]]"
---
## Headerdatei
### CIN / COUT
`#include <iostream>`

### Manipulationen
`#include <iomanip>`

## Ausgabeformatierung

### Allgemein

| C++                              | Beschreibung                                                 |
| -------------------------------- | ------------------------------------------------------------ |
| setfill(Zeichen in Hochkommatas) | setzt das Füllzeichen (dauerhaft)                            |
| setw(Ganzzahl $n$)               | setzt die Feldbreite für die nächste Operation auf n Spalten |
| left / right                     | linksbündige / rechtsbündige Ausgabe                         |
| internal                         | bei Zahlen: Vorzeichen links-, Wert rechtsbündig             |

### Manipulatoren bei Ganzzahlen

| C++                     | Beschreibung                                      |
| ----------------------- | ------------------------------------------------- |
| dec                     | dezimale Darstellung (Standard)                   |
| hex                     | hexadezimale Darstellung                          |
| oct                     | oktale Darstellung                                |
| showpos / noshowpos     | + bei positiven Zahlen ausgeben / unterdrücken    |
| uppercase / nouppercase | Groß- /Kleinbuchstaben (Standard) bei Hex-Ausgabe |

## Beispiele

```cpp
#include <iostream>
#include <iomanip>

using namespace std

int main(){
	int n = 4;
	cout << showpos << n; //Ausgabe: "+4"
	cout << setw(3) << n; //Ausgabe: "  4"
	cout << setfill(0) << setw(2) << n; //Ausgabe: "04"

	float f = 5;
	cout << showpoint << f; //Ausgabe: "4.0000000"
	cout << setprecition(4) << f; //Ausgabe: "4.000"
	
	cout << endl; //Ausgabe: Macht eine neue Zeile

}
```

## Eingaben

```cpp
char antwort; 
int k, ergebnis; 
cout << "Geben Sie bitte einen Buchstaben und eine Zahl durch Leerzeichen getrennt ein: "; 
cin >> antwort >> k; 
cout << "Es wurde antwort="<< antwort<< " und k=" << k << "eingegeben\n";
```

>CIN macht nach der Eingabe automatisch eine neue Zeile