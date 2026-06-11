---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[C++]]"
---
## Variablenarten

### Ganze Zahlen

Bei `signed` Werten:

| Datentyp                         | Größe  | Wertebereich             |
| -------------------------------- | ------ | ------------------------ |
| `short` oder `short int`         | 16 Bit | $-2^{15}$ bis $2^{15}-1$ |
| `int`                            | 32 Bit | $-2^{31}$ bis $2^{31}-1$ |
| `long` oder `long int`           | 32 Bit | $-2^{31}$ bis $2^{31}-1$ |
| `long long` oder `long long int` | 64 Bit | $-2^{63}$ bis $2^{63}-1$ |

## Reelle Zahlen (Gleitkommazahlen)

>In der Regel wird hier `double` verwendet

| Datentyp | Größe  | Gültige Stellen | Zahlenbereich                                                               |
| -------- | ------ | --------------- | --------------------------------------------------------------------------- |
| `float`  | 32 Bit | 7               | $-3,4*10^{38}$ bis $-3,4*10^{-38}$ und $3,4*10^{-38}$ bis $3,4*10^{38}$     |
| `double` | 64 Bit | 15              | $-1,7*10^{308}$ bis $-1,7*10^{-308}$ und $1,7*10^{-308}$ bis $1,7*10^{308}$ |

## Wahrheitswerte

Für Wahrheitswerte verwendet man `bool` . Dieser Datentyp kennt nur `true` oder `false` 

## Einzelne Zeichen

Für einzelne Zeichen gibt es den Datentyp `char` . Er speichert den Code des Zeichens als ganze Zahl mit 8 Bit. Ein `char` kann mit [[Mathematische Ausdrücke#Inkrement und Dekrement|Inkement oder Dekrement]] hoch/runtergezählt werden

```cpp
char a = 'A';
a++; //jetzt steht in a der Wert 'B'
a = a + 2; // jetzt steht in a der Wert 'D'
```

## Gültigkeit von Variablen

>Eine Variable gilt ab der Stelle, an der sie definiert wird, bis zum Ende des Blocks (nächste geschweifte Klammer zu "}" )

```cpp
int main(){
	int a; //Definition
	a = 2; //Deklaration

	int i = 1; //Beides Gleichzeitig
	
	if(a < 3){
		int a = 5; //a wird neu deklariert
		cout << a << endl; //5 wird ausgegeben
	}
	cout << a; // 2 wird ausgegeben
}```

# Datentypen mit vorgegebener Breite

#### Bibliothek
`cstdint`

| Muster für den Datentyp    | Bedeutung                                                                                                                                                       |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| intN_t uintN_t             | Ein int-Wert mit einer Breite von exakt N Bits. Dieser Typ ist optional und wird nicht vom aktuellen Standard gefordert. Beispiel: uint8_t hat genau 8 Bit.     |
| int_leastN_t uint_leastN_t | Ein int-Wert mit einer Breite von mindestens N Bits. Beispiel: uint_least16_t hat mindestens 16 Bit.                                                            |
| int_fastN_t uint_fastN_t   | Der schnellste int-Typ mit mindestens einer Breite von N Bits. Beispiel: int_fast32_t ist der schnellste Ganzzahltyp mit Vorzeichen, der mindestens 32 Bit hat. |
| intmax_t uintmax_t         | Größtmöglicher ganzzahliger Typ.                                                                                                                                |

## Beispiel

```cpp
intmax_t i = -1; 
uintmax_t u; 
u = i;
```

Die Zuweisung u = i kopiert das Bitmuster von i nach u, __ohne__ auf den Wert zu achten.

# Spezielle Datentypen

### size_t
`size_t` passt sich automatisch an die Plattform an. Es ist ein unsigned Interger von unterschiedlicher Größe