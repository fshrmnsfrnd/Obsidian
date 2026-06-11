---
Fach:
Thema:
  - "[[Knowledge Base/Netzwerktechnik/Switching/Switching|Switching]]"
---
>**IEEE 802.1d**
>Das Spanning-Tree-Protokoll existiert heute hauptsächlich in den Ausprägungen Rapid Spanning Tree (RST) und Rapid per VLAN Spanning Tree oder Multiple Spanning Tree (MST), da die ursprüngliche Form des Spanning Trees zu hohen Konvergenzzeiten und damit in komplexen Topologien zu Ausfällen von 30 bis 50 Sekunden führt.

STP soll das Auftreten von doppelten Frames in einem geswitchten Ethernet-Netzwerk verhindern. 
Es sorgt dafür, dass keine Netzwerkschleifen (Loops) entstehen, denn durch einen Broadcast-Sturm führen sie innerhalb kürzester Zeit zur Überlastung eines Netzwerksegments. Ethernet-Frames haben im Gegensatz zu IP-Paketen keine maximale Lebensdauer (Time to Live, TTL) und bewegen sich deshalb potenziell unendlich lange im Kreis.

>Das Spanning-Tree-Protokoll erreicht die Schleifenfreiheit, indem es bestimmte Verbindungen zwischen Switches deaktiviert. Abbildung 1 zeigt drei Beispiele (A, B, C) für Netzwerktopologien, die ohne die Blockade einiger Switchports durch Spanning Tree zum Zusammenbruch des Netzwerks führen würden.

![[Pasted image 20260108145733.png]]

> [!NOTE] Broadcast Stürme
> Auch Broadcast-Stürme können in redundanten Topologien auftreten. Wenn Station A eine Broadcast, z.B. eine ARP-Anfrage sendet, wird diese über alle Ports von Switch 1 und Switch 2 geflutet. Switch 2 flutet seinerseits alle Broadcasts, die er von Switch 1 und Switch 3 erhält und veranlasst somit Switch 1 und Switch 3 wiederum neue Broadcasts auszusenden. somit ist das Netzwerk nur damit beschäftigt, Broadcasts zu versenden, was zu einem Totalausfall führt, bis einer der Switches vom Netz genommen wird.

STP basiert auf dem regelmäßigen Austausch von Konfigurationspaketen (Bridge Protocol Data Units, BPDU) mit festgelegter Zieladresse (01-80-C2-00-00-10). 

## Wahlen ohne Demokratie
Die Berechnung des Spanning Trees erfolgt in drei wesentlichen Schritten:
- Wahl der Root Bridge,
- Wahl der Root Ports,
- Wahl der Designated Ports.

In einem Spanning Tree nimmt jeder Port eines Switches eine von **vier möglichen Rollen** ein:
- **Root Port**
	- Aktiver Switchport, dessen Upstream in Richtung Root Bridge zeigt. Jeder Switch besitzt **maximal einen** Root Port.
- **Designated Port**
	- Aktiver Port, der **weg** von der Root Bridge (Downstream) zeigt.
- **Alternate Port** (nur bei Rapid Spanning Tree)
	- Zeigt ebenfalls zur Root Bridge, ist aber nicht aktiv (Blocked).
- **Backup Port** (nur bei Rapid Spanning Tree)
	- Verbindung zu einem anderen Switch, der über einen anderen Switchport günstiger erreicht werden kann; ebenfalls nicht aktiv (Blocked).

Die Ports können einen von **zwei** Modi haben:
- **Status Forwarding**
	- Ist offen und funktioniert normal
- **Status Blocking**
	- Blockt den Netzwerkverkehr auf diesem Port, um Loops zu vermeiden.

### Wahl der Root Bridge
>Die Parameter kann der Netz-Admin in der Regel konfigurieren, ebenso gewünschte Prioritäten und Wegekosten, um bevorzugte Routen zu bilden.

Die Wahl der Root Bridge erfolgt mit der Bridge-ID, die aus drei Bestandteile hat:
- Bridge Priority
	-  0 bis 61440 in Schritten von 4096
- System-ID-Extension
	- Ist die VLAN Nummer
- MAC-Adresse
Root Bridge wird der Switch mit der **niedrigsten** Bridge Priority
Sollten mehrere Switche die selbe Bridge Priority haben, wird unter denen mit der niedrigsten anhand der niedrigsten System-ID-Extension und MAC entschieden.

Die Ports der redundanten Strecken schalten die Switches ab und reaktivieren sie erst beim Ausfall der Hauptroute.

Nachteilig an STP und RSTP ist, dass sie entweder nur einen Baum für alle VLANs oder für jedes VLAN einen eigenen Baum bilden müssten, wobei erhöhter BPDU-Datenverkehr aufkommt. Erst mit Multiple Spanning Tree (MSTP) kann man Topologien erstellen, die mehrere VLANs zusammenfassen.
# BPDU Guard
---
Der BPDU Guard deaktiviert einen Switchport, sobald er eine BPDU empfängt. 
Der Guard eignet sich für Ports, an denen keine Pakete von Switches **ankommen** sollten.
## Konfgurieren
Auf einem Port aktivieren
```cli
interface FastEthernet0/1
spanning-tree bpduguard enable
```
Global aktivieren
```cli
spanning-tree portfast bpduguard default
```
# Etherchannel mit LACP (Link Aggregation Control Protocol)
---
>Mit Etherchannel lassen sich mehrere physische Verbindungen zwischen 2 Switchen zu einer logischen zusammenzufassen, um die Bandbreite zu erhöhen und eine Redundanz zu schaffen

Andere Bezeichnungen für Ether Channel:
- Link Aggregation
- Bonding
- Teaming
- Trunk
- PAgP (Cisco Proprietär)
> [!NOTE] Link Aggregation ist in IEEE 802.3ad beschrieben
## Einrichten
```cli
interface FastEthernet0/1
channel-protocol lacp
channel-group 1 mode active
!

interface FastEthernet0/2
channel-protocol lacp
channel-group 1 mode active
```
 Jeder Etherchannel bekommt eine eindeutige ID (Channel Group)
## Anzeigen
```cli
Switch1# show etherchannel
Channel-group listing:
----------------------
Group: 1
----------
Group state = L2
Ports: 2 Maxports = 16
Port-channels: 1 Max Port-channels = 16
Protocol: LACP
```

```cli
Switch1#show lacp neighbor
Flags: 
S - Device is requesting Slow LACPDUs
F - Device is requesting Fast LACPDUs
A - Device is in Active mode 
P - Device is in Passive mode
Channel group 1 neighbors
Partner's information:
Port   Flags LACP port Priority Dev ID         Age Oper Key Port Number Port State
Fa0/1  SA    32768              001e.bde6.3100 0s  0x1      0x2         0x3D
Fa0/2  SA    32768              001e.bde6.3100 3s  0x1      0x3         0x3D
```