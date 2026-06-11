---
tags:
Fach: "[[Programmieren]]"
Thema:
  - "[[C++]]"
---
# Headerdatei
`#include <SFML/Graphics.cpp>`
# Klassen

## RenderWindow
## Constructor
`RenderWindow window(sf::VideoMode(breite, höhe), "Name des Fensters")`

## Event

## Shapes
## Allgemeine Memberfunctions
- `.setPosition(x, y)`
- `setFillColor(sf::Color::Red)`
## CircleShape
### Constructor
`CircleShape kreis(radius)`
## RectangleShape
### Constructor
`RectangleShape viereck(Vector2f(x, y))`
## Memberfunctions
`.setRotation(<angle>)`


# Fenster aktualisieren
```cpp
while(window.isOpen()){ //Endlosschleife solange das Fenster offen ist
	Event event;
	while(window.pollEvent(event)){
		if(event.type == Event::Closed){ //Sauberes schließen
			window.close();
		}
	}
	window.clear();
	window.draw(kreis);
	window.draw(viereck);
	window.display();
}
```