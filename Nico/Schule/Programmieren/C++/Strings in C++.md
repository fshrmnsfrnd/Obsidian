---
Thema:
  - "[[C++]]"
---
# Headerdatei
`#include <string>`

# String einlesen
Mit `cin` ist einlesen nur bis zum ersten Leerzeichen möglich
Besser `getline(cin, stringname)` verwenden.

Wenn zuerst eine Zahl mit `cin` eingelesen wurde, muss vor `getline()` ein `cin.ignore()` ausgeführt werden, um gepufferte Steuerzeichen zu löschen

# Teil eines Strings abrufen

`string a = s.substr(1, 2);`
1 heißt ab dem zweiten Zeichen, und 2 heißt zwei Zeichen.

# Vergleichen
Es wird Buchstabe für Buchstabe verglichen, es geht um den Unicode Wert der Zeichen.

# Memberfunctions
## .length()
 gibt die Anzahl der enthaltenen Zeichen zurück.

## .at()
Gibt das Zeichen an der Angegebenen Stelle zurück. 
Z.B. `s.at(0)` gibt das erste Zeichen zurück

## .substr()
`string a = s.substr(1, 2);`
1 heißt ab dem zweiten Zeichen, und 2 heißt zwei Zeichen.