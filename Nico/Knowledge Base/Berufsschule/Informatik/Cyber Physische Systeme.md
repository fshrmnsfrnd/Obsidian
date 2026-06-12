---
Fach: "[[Berufsschule]]"
Thema:
  - "[[Embeddes Systems]]"
---
Ein CPS (**C**yber **P**hysisches **S**ystem) ist ein Zusammenschluss intelligenter, vernetzter Steuerungssysteme. Es besteht aus einem **Sensor**, einem **Embedded System** / [[#SBC]] und einem **Aktor**.  

Der Sensor überprüft einen Zustand, z. B. die Temperatur eines Raumes. Der SBC verarbeitet dieses Ereignis und gibt dem Aktor eine Aufgabe, die er machen soll, z. B. die Heizung aktivieren.  

Klassische Anwendungsfälle für ein CPS sind z. B. Industrielle-Fertigungs-Hallen oder Smart-Home (IoT).  

Die Sicherheit, dieser Systeme nimmt durch schnelle Zunahme an Angriffen und IoT-Maleware immer mehr ab.
# SBC
---
Ein SBC ist ein **S**ingle **B**ord **C**omputer, sie werden auch **Embedded System** genannt z. B. eine Raspberry Pi, Arduino. 
Diese verwenden häufig die Programmiersprachen:
- Python
- Java
- C

In der Industrie werden häufig **SPS**, also **S**peicher **P**rogrammierbare **S**teuerungen verwendet. 
Diese verwenden häufig die Programmiersprachen:
- FUP/FBS
- AWL
- KOP

Ein SBC hat immer einen [[#Microcontroller]]. Ein Betriebssystem für einen solchen Controller ist z. B. NodeMCU.
## Aufbau eines SBC
![[ANeZp4coQ--700.webp]]
# Übertragung
---
## Arten
IoT verwendet viele verschiedene Übertragungsmöglichkeiten / Protokolle.
- Drahtlos:
    - WLAN
    - ZigBee
    - Bluetooth
- Leitergebunden
    - Ethernet
    - CAN
    - KNX
## Bridge
Oft muss zwischen den verschiedenen Protokollen gewechselt werden, z. B. von Ethernet auf WLAN.
- Philips Hue (WLAN zu ZigBee)
- AccessPoint (WLAN zu Ethernet)
## MQTT
MQTT ist ein Protokoll, das häufig von IoT verwendet wird. Es dient zur schnellen Übertragung von Informationen.
### Aufbau
![[Bg3yF1GCXI-518.webp]]

| **Begriff** | **Bedeutung**                                  | **Beispiel**              |
| ----------- | ---------------------------------------------- | ------------------------- |
| Publisher   | Sensor                                         | Thermometer               |
| MQTT Broker | Verarbeiter/SBC                                | Raspberry Pi              |
| Subscriber  | Aktor                                          | Schalter                  |
| Topic       | Thema, das vom Subscriber aboniert werden kann | Temperatur, Bewegung, ... |
# Node Red
---
[Node Red](https://nodered.org/) ist eine Entwicklungsumgebung für IoT Programme. Anders als bei normalen IDEs wird kein Code geschrieben, sondern generiert nach dem der Nutzer die einzelnen Teile in die richtige Reihnfolge gezogen hat.
## Vor- und Nachteile

|**Vorteile**|**Nachteile**|
|---|---|
|Einfach zu Benutzen|Neu Teile müssen erst Programmiert werden|
|keine Vorerfahrung nötig|schneller Verlust der Übersicht bei großen Programmen|
# Wichtige Zusatzinformationen
---
## Analog vs Digital
Ein **Analoge**-Signal ist ein Stufenloses Signal. Ein **Digitales**-Signal kann nur zwei Werte annehmen. Um die Werte von dem einen in das andere umzuwandeln wird ein **D**igital-nach-**A**nalog-Wandler (**D/A-Wandler**) eingesetzt.
## Schnittstelle vs Bus
An eine **Schnittstelle** kann nur **EIN** Gerät angeschlossen werden. An einen **Bus** jedoch **MEHRERE**.
## Feldbus
Busse die beim Automatisierungs- und Steuerungssysteme verwendet werden werden auch Feldbus genannt.  
**Beispiele:**
- Ethernet: Kommunikation im Netzwerk
- CAN: Multi-Master Busteilnehmer wie Sensoren und Aktoren(Alle sind gleich berechtigt)
- KNX: häufig in der Gebäudeautomatik und unterstützt große Reichweiten.
## Microcontroller
Ein Microcontroller ist ein Halbleiterchips der einen Prozessor und Peripheriefunktionen (spezifische auf eine Aufgabe angepasst Teile) hat, z. B. ein WLAN-Modul.
### Schnittstellen und Busse
Mikrocontroller verwenden folgende Schnittstellen und Busse:

|**Name**|**Aufgabe**|
|---|---|
|UART|Bereitstellung einer Digitalen Schnittstelle|
|I2C|Datenbus zur Internen Kommunikation eines Chips|
|GPIO|selbst konfigurierbare Inputs und Outputs (Raspberry PI GPIO)|
