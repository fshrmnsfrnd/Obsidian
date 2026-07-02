---
Thema:
  - "[[C++]]"
---
# Quellcode Dateien

In Quellcode-Dateien mit der Endung `.cpp` oder `.c` stehen Funktionen, darunter auch das Hauptprogramm.
# Header Dateien

Header-Dateien mit der Endung .h enthalten Funktionsprototypen, Präprozessor-Konstanten und ähnliches. Zu jeder Quellcode-Datei `xyz.cpp` - ausgenommen das Hauptprogramm - sollte es eine Header-Datei `xyz.h` geben.

Hier kein `using namespace ...` verwenden!

## Mehrfaches Einbinden vermeiden 

Am Anfang von Header-Dateien können Sie bei manchen Präprozessoren ==`#pragma once`== schreiben. Das sorgt dafür, dass die Datei garantiert nur einmal pro Quellcode-Datei eingebunden wird. Leider gehört diese Anweisung nicht zum C++-Standard. 

Wenn der Präprozessor sie nicht versteht, muss man eine andere Konstruktion verwenden: 
```cpp
#ifndef DATEINAME_H // ifndef = if not defined 
#define DATEINAME_H // Dateinamen als leere Konstante definieren 
	// ... eigentlicher Inhalt der Header-Datei ... 
#endif
```

# Einbinden

`#include "headerdatei.h"`

Für Headerdateien im selben Projekt werden "" verwendet.

# Beispiel

Module.cpp:
```cpp
#include "Module.h"

int modulefunction(int a){
	return a + 1;
}
```

Module.h:
```cpp
#pragma once

int modulefunction(int a);
```

Main.cpp:
```cpp
#include <iostream>
#include "Module.h"

using namespace std;

int i = 1;
cout << modulefunction(i); //gibt "2" aus
```