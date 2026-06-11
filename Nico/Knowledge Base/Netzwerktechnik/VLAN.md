---
Fach: "[[Berufsschule]]"
Thema:
  - "[[Networks]]"
---
VLAN steht für _**V**irtual **L**ocal **A**rea **N**etwork_. Vlans werden benutzt um Bestehende Netzwerke auf OSI-Layer 2 nochmal zu unterteilen. Dafür wird ein Hardware-Switch in mehrere Virtuelle-Switche aufgeteilt. Um VLANs aus anderen VLANS zu erreichen muss man zwischen Ihnen Routen
# Arten von VLAN
---
## Tagged
Bei einem Tagged VLAN wird an das IP-Pakete eine VLAN-ID angehängt, mit der dann das Paket einem VLAN zugeordnet werden kann.

| **Vorteile**  | **Nachteile**                   |
| ------------- | ------------------------------- |
| Weniger Ports | Langsamer                       |
|               | Weniger Sicherheit als Untagged |
## Untagged
Beim Untagged VLAN werden Ports von einem Switch einem VLAN zugeordnet.  
Z. B. Wird den bei einem 8-Port-Switch Port 1 bis 4 dem VLAN 10 und Port 5 bis 8 dem VLAN 20 zugeteilt.

| **Vorteile** | **Nachteile**       |
| ------------ | ------------------- |
| Schneller    | Benötigt mehr Ports |
| Sicherer     |                     |
![[Pasted image 20260105173624.png]]
## Statisch
Beim statischen VLAN wird einem Port wie oben erwähnt ein Fixes VLAN zugeordnet.

| **Vorteile**             | **Nachteile**               |
| ------------------------ | --------------------------- |
| Einfach zu Konfigurieren | kann leicht umgangen werden |
| Geringer Wartungsaufwand |                             |
## Dynamisch
Beim dynamischen VLAN wird das VLAN MAC-Adressen zugeordnet, dadurch entscheidet das angeschlossene Gerät, welches VLAN verwendet wird.

|**Vorteile**|**Nachteile**|
|---|---|
|Sicherer|Schwieriger zu Konfigurieren|
# Trunkport
Beim [[Knowledge Base/Netzwerktechnik/Switching]] von VLANs gibt es vorallem bei Untagged VLANs das Problem, dass sehr viele Ports benötigt werden. _(siehe Bild 1)_  
![[Pasted image 20260105173634.png]]
Daher wurde der Trunkport erfunden. Dabei wird von dem Switch ein VLAN als Trunk-Port konfiguriert. Dieser Port ist dann Tagged. Überdiesen Port werden dann alle anderen VLANS an einen anderen Switch weitergegeben. der dann die Paket wieder dem richtigen VLAN zuordnen kann. _(siehe Bild 2)_  
![[Pasted image 20260105173636.png]]