---
Fach:
Thema:
  - "[[Knowledge Base/Netzwerktechnik/Switching/Switching|Switching]]"
---
Managebare Switches bieten in der Regel **V**irtual **L**ocal **A**rea **N**etworks. Damit kann man auf Layer 2 die Teilnehmer logisch gruppieren.

**Vorteile:**
- Das Netzwerk wird in mehrere Broadcast-Domänen unterteilt
- VLANs sind untereinander abgeschottet
## Konfiguration
### Port basiert
Jeder Port wird manuell einem VLAN zugeordnet. Das ist sehr **unflexibel**.
### Tagged VLAN
>IEEE 802.1q

Hier wird der **Ethernet Header** verändert. Es kommen 4 Bytes hinzu.
Man packt eine feste 16Bit **Kennung** sowie einen 16Bit **Tag** in den Header. 
Zwölf Bits des Tags dienen zur Kennzeichnung des VLAN. Da zwei Werte (0 und 4095) reserviert sind, kann man **maximal 4094** virtuelle LANs nutzen. 
**VLAN 1** ist als **Standard-VLAN** vordefiniert, dem **alle Ports** angehören. 
In den restlichen vier Bits stecken eine fixe Kennung sowie drei variable Bits für Prioritätssteuerung (Quality of Service, IEEE 802.1 p).

