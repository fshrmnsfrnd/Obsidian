---
Fach:
Thema:
  - "[[Networks]]"
---
> Switches arbeiten auf **Layer 2**
# Ablauf
---
1. Paket kommt auf einem Port an
2. Switch überprüft ob die **Source Mac** bereits im **Switching Table** ist
	1. Wenn **Nein** wird im Switching Table die Zuordnung **MAC <=> Port** gespeichert
3. Switch schaut im Switching Table nach der **Destination MAC**
	1. Gefunden: Switch schickt das Paket durch den gefunden **Port**
	2. Nicht Gefunden: Wird an alle Ports weitergeleitet (**flooding**) 

# Switching Table
---
- Hier werden die gelernten **Source Macs** und deren **Port** gespeichert
- Pro Port können **viele MACs** gespeichert werden (Anderer Switch am Switchport)
- **Aging**: Nach einer bestimmten Zeit werden Record wieder **gelöscht** (typisch 300 Sekunden)
# Arten von Switchen
---
- **Access** Switch
	- Hier werden Endgeräte angeschlossen
	- z.B. für eine Etage
- **Distribution** Switch
	- Verbindet mehrere Access Switche
- **Core** Switch
	- Höchstleistungsswitch
	- Verbindung von Distribution Swwitches
	- In Großen Netzwerken
# Latenz
---
Durch das Zwischenspeichern erscheinen die Ethernet-Frames immer mit einem kleinen Zeitverzug am Ausgangs-Port (Latenz, Latency); dabei passieren kleine Pakete von 128 Byte den Switch schneller als große 1518er Frames, weil sie früher vollständig in seinem Speicher vorliegen. Typisch sind gute Werte von 3-5$\mu$s für kleine Frames und 13-24$\mu$s für große. 

>[!Note]
Selbst wenn die Daten durch fünf Switches hindurch müssen, liegt das noch um den Faktor 2000 unterhalb der bei VolP-Telefonie maximal tolerierbaren Verzögerung von 240 ms.
