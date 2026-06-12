---
Fach: "[[Berufsschule]]"
Thema:
  - "[[Storage]]"
---
# DAS
---
Das **DAS** (**D**irect **A**ttatched **S**torage)ist das üblichste Speichersystem, dass in den meisten Computern verwendet wird. Dabei ist die Festplatte **direkt** mit dem Computer Verbunden.

![[Pasted image 20260105173831.png]]

|**Vorteile**|**Nachteile**|
|---|---|
|günstig|keine flexibelität|
||kein Remote-Zugriff|

# NAS
---
Beim **NAS** (**N**etwork **A**ttatched **S**torage) wird ein Laufwerk über das Netzwerk mittels eines Protokolls wie z. B: **SMB**, **WebDAV**, **FTP** eingebunden. Die Daten werden dabei **Dateiorientiert** versendet, da die Aufteilung auf die Blocks von dem Server erledigt wird (**Dateisystem ist ebenfalls ausgelagert**).
![[6d1IMPudT5-501.webp]]

|**Vorteile**|**Nachteile**|
|---|---|
|Remoter-Zugriff|abhängig von Netzwerkgeschwindigkeit|
||belastet das Netzwerk|

# SAN
---
Hier werden die Daten ebenfalls auf einen Remoten-Speicher abgelegt. Im gegensatz zur NAS, wird beim **SAN** (**S**torage **A**rea **N**etwork) das Dateisystem **NICHT** auf den Server ausgelagert. Die Datenübertragung ist hier **Blockorientiert**. Hier werden Technologien wie **FC** (**F**ibre **C**hannel), **FCoE** (**F**ibre **C**hannel **o**ver **E**thernet) oder **iSCSI** (**I**nternet **SCSI**)

![[bPTS2jmIHm-505.webp]]

|**Vorteile**|**Nachteile**|
|---|---|
|redundant|teuer|
|skalierbar|kleinere Reichweite|
||höherer Aufwand|

# Technologien
---
## Fibre Channel

|               |                                                                                 |
| ------------- | ------------------------------------------------------------------------------- |
| **Frame**     | ![[QMT8cf9NNE-700.webp]]                                                        |
| **Vorteile**  | - kleiner Frame -> schnell                                                      |
| **Nachteile** | - teuer  <br>- benötigt spezielle Hardware  <br>- maximale Reichweite von 1,2km |
## Fibre Channel over Ethernet

|               |                                                                                 |
| ------------- | ------------------------------------------------------------------------------- |
| **Frame**     | ![[7y9QGxQtk6-700.webp]]                                                        |
| **Vorteile**  | - es können normale (Ethernet-)Switche verwendet werden  <br>- günstiger als FC |
| **Nachteile** | - recht teuer  <br>- maximale Reichweite von 1,2km                              |
## Internet SCSI

|               |                                                                                       |
| ------------- | ------------------------------------------------------------------------------------- |
| **Frame**     | ![[xTdtWOI7hs-700.webp]]                                                              |
| **Vorteile**  | - hohe Reichweite  <br>- normale Netzwerktechnik kann verwendet werden  <br>- günstig |
| **Nachteile** | - je anch Aufbau belastet restliches Netzwerk  <br>- langsam                          |
# Wichtige Begriffe
---

| **Begriff**      | **Bedeutung**                                                                                            |
| ---------------- | -------------------------------------------------------------------------------------------------------- |
| LUN              | **Speichereinheiten** in einem SAN (**virtuelle** Festplatten)  <br>![[Pasted image 20260105173942.png]] |
| iSCASI-Target    | iSCSI-**Server**                                                                                         |
| iSCASI-Initiator | iSCSI-**Client**                                                                                         |
| Volume Manager   | ein **Volume Manager** ermögicht das dynamische **vergrößern** und **verkleinern** während dem Betrieb.  |