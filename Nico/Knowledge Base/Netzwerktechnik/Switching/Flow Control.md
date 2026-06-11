---
Fach:
Thema:
  - "[[Knowledge Base/Netzwerktechnik/Switching/Switching|Switching]]"
---
Beim Switching tritt **Überlastung** auf, wenn das Netzwerk mehr Datenverkehr erfährt, als es effizient verarbeiten kann, was zu Verzögerungen und Verlust von Datenframes führen kann. 

Um solche Situationen beim Switching zu bewältigen und die Netzwerkstabilität und -leistung zu gewährleisten, kommen verschiedene Technologien zum Einsatz. Diese Funktionen sind darauf ausgerichtet, den Datenfluss zu regulieren, Engpässe zu vermeiden und die Effizienz des Netzwerks auch unter hoher Last zu erhalten.

>IEEE 802.3x

Welche Flow Control genutzt wird, entscheiden die Kommunikationspartner während des Link-Aufbaus per Auto negotiation.
# Back-Pressure
---
Back-Pressure wird speziell in **Halbduplex**-Netzwerktechniken eingesetzt. Wenn der Switch Überlastung feststellt, sendet er ein JAM Signal, was eine **Kollision** simuliert. Dadurch wartet das andere Gerät einige Zeit bis zum senden des nächsten Pakets.
# Pause Frames
---
Pause Frames sind fixe MAC-Control-Pakete, die stets als Multicast an die Adresse `01-80-C2-00-00-01`  gehen und im Length/Typ-Feld den Wert ``88-08`` enthalten.
Pause Frames funktionieren ausschließlich im **Vollduplex**-Modus von Fast-Ethernet und Gigabit-Ethernet. Sie passen die Übertragungsrate an die Kapazität des Empfängers an, um Datenstau und möglichen Datenverlust zu vermeiden.