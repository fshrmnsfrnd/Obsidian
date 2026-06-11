---
Thema:
  - "[[Neural Networks]]"
---
Ein einzelnes Neuron ist so aufgebaut:
![[Pasted image 20260304231654.png]]

#  Aktivierungsfunktionen
Es gibt eine Vielzahl von verschiedenen **Aktivierungsfunktionen**. Diese bestimmen wann ein Neuron ein Ergebnis weitergibt. Diese Funktionen sind einfache **nicht** lineare Funktionen.  
## Arten der Aktivierungsfunktion:
![[Pasted image 20260304231945.png]]
### ReLU (Rectified Linear Unit)
Die ReLU Funktion hat sich in letzter Zeit bei Neuronalen Netzen etabliert.
Hier weden negative Werte durch $0$ ersetzt
### Softmax
Eine weitere verbreitete Funktion ist die Softmax Aktivierungsfunktion. 
Diese Funktion wird oft als **letzte** bei **Klassifikationsaufgaben** verwendet. 
Sie bildet aus den Eingabewerten Wahrscheinlichkeiten.

### Sigmoid
Wenn es nur **zwei Eingabewerte** gibt verwendet man die **Sigmoid** Funktion.

Der Unterschied zwischen beiden Funktionen ist, dass bei der **Softmax** Funktion der Kurvenverlauf bei 0 noch **unterhalb** von 0,5 liegt.
![[image-23-e1667663718858-768x353.webp]]
