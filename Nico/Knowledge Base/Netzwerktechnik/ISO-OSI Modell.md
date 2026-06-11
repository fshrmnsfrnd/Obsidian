---
Fach:
tags:
Thema:
  - "[[Networks]]"
---
>Das **ISO-OSI-Modell** oder auch kurz **OSI-Modell** wird verwendet um die einzelnen Aufgaben der Kommunikation in einem Netzwerk als **Schichten** bzw. **Layer** da zu stellen. Es dient als **Hilfe** in der **Entwicklung** von neuen Netzwerkprotokollen und erhöht die **Kompatibilität** und **Interoperabilität** der Geräte und Protokolle verschiedener Hersteller.
# Aufbau
---

| **Nr** | **Name der Schicht**                        | **Funktion**                                                     | **Protokolle**                       | **Hardware**         | **Bezeichnung der** **P**rotocol **D**ata **U**nit |
| ------ | ------------------------------------------- | ---------------------------------------------------------------- | ------------------------------------ | -------------------- | -------------------------------------------------- |
| 7      | **Application Layer**                       | Bereitstellen von Netzwerkdiensten für Answendungen              | FTP, SFTP, [[DNS]],<br>SSH, ...      |                      | Daten                                              |
| 6      | **Presentation Layer**                      | Datenformatierung,<br><br>Verschlüsselung<br><br>und Kompression | SSL/TLS, JPEG, GIF, <br>HTTPS<br>... |                      | Daten                                              |
| 5      | **Session Layer**                           | Aufbau, Verwaltung und Beendigung von Sessions                   | NetBios, RPC                         |                      | Daten                                              |
| 4      | **Transport Layer**                         | Verbindungsorientierte bzw. Verbindungslose Datenübertragung     | TCP, UDP                             | Firewall             | Segment                                            |
| 3      | **Network Layer**                           | Routing und logische Adressierung                                | IPv4, IPv6                           | Router, L3-Switch    | Paket oder Datagramm                               |
| 2      | **<br><br>Data Link Layer<br><br><br><br>** | Fehlererkennung und Rahmenbildung                                | Ethernet                             | Switch, Hub          | Frame                                              |
| 1      | **<br><br>Physical Layer<br><br><br><br>**  | Übertragung von Bits über ein Medium                             | Bits                                 | Kabel, Netzwerkkarte | Bit oder Symbol                                    |
## Physical Layer
---
Auf dieser Schicht geht es nur um die reine Hardware und die Bits die über sie fließen.  
## Data Link Layer
---
Hier findet die Kommunikation über Hardwareadressen (**MAC-Adressen**) statt. Diese Adressen sind **Weltweit eindeutig** und **6 Byte** lang, wobei das: 
- **U/L-Bit** zeigt ob eine Adresse **einmalig** oder **lokal verwaltet** ist  
- **I/G-Bit** kennzeichnet ob es ein **Unicast** oder ein **Multi-** bzw. **Broadcast** ist

Die **Präambel** im Header eines Layer 2 Frames dient zur Synchronisation des Takt-Oszillators des Empfängers.

Die Daten auf dieser Ebene nennt man **Frame**. [Ethernet]([[Ethernet Standards]]) hat 4 mögliche Rahmenformate, die drei Häufigsten sind so aufgebaut:  
![[Pasted image 20251123002742.png]] 
### ETHERNET II 

| **Bestandteil**  | **Aufgabe**                                                                                                        |
| ---------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Präambel**     | Synchronisation für den Takt (7 Byte), sagt wann die Zieladresse Beginnt (1 Byte **SPD** Starting Frame Delimiter) |
| **Zieladresse**  | MAC-Adresse vom Empfänger                                                                                          |
| **Quelladresse** | MAC-Adresse vom Sender                                                                                             |
| **Typ**          | Art des Protokolls für Layer 3 (z. B. 0800 (IPv4), 0860 ([[ARP]]), 86DD (IPv6)                                         |
| **Daten**        | Daten + Informationen der darüber liegenden Layer                                                                  |
| **CRC**          | ([[Cyclic Redundancy Check]]) Prüfsumme um zu Berechnen ob der Frame korrekt übertragen wurde                          |

### ETHERNET 802.3

| **Bestandteil**  | **Aufgabe**                                                                                                        |
| ---------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Präambel**     | Synchronisation für den Takt (7 Byte), sagt wann die Zieladresse Beginnt (1 Byte **SPD** Starting Frame Delimiter) |
| **Zieladresse**  | MAC-Adresse vom Empfänger                                                                                          |
| **Quelladresse** | MAC-Adresse vom Sender                                                                                             |
| **Länge**        | Beschreibt die Anzahl der Oktette zwischen Ende des Längen-Feldes und dem CRC-Feld                                 |
| **Daten**        | **LLC** (DSAP + SSAP-Wert mit Infos über Layer 3 Protokoll) + Daten + Informationen der darüber liegenden Layer    |
| **CRC**          | ([[Cyclic Redundancy Check]]) Prüfsumme um zu Berechnen ob der Frame korrekt übertragen wurde                          |

### ETHERNET 802.1p/1q  

| **Bestandteil**         | **Aufgabe**                                                                                                        |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Präambel**            | Synchronisation für den Takt (7 Byte), sagt wann die Zieladresse Beginnt (1 Byte **SPD** Starting Frame Delimiter) |
| **Zieladresse**         | MAC-Adresse vom Empfänger                                                                                          |
| **Quelladresse**        | MAC-Adresse vom Sender                                                                                             |
| **TPI**                 | (Tag-Protocol-Identifier) Kennzeichnet das es sich um ein Frame mit **VLANs** handelt ($0x8100$)                   |
| **TAG**                 | oder auch **TCI** (Tag-Control-Information)                                                                        |
| **TYPE**                |                                                                                                                    |
| **Daten**               | Daten + Informationen der darüber liegenden Layer                                                                  |
| **CRC**                 | ([[Cyclic Redundancy Check]]) Prüfsumme um zu Berechnen ob der Frame korrekt übertragen wurde                          |
| **Bestandteil des TAG** | **Aufgabe**                                                                                                        |
| **Priority**            | Kennzueichnet die Prioriätt (Class of Service bzw. **CoS**)                                                        |
| **TR**                  | Kann für ein Token-Ring-Encapsulation-Prozess verwendet werden                                                     |
| **VLAN-ID**             | Id des VLANs (da zwei IDs reserviert sind gibt es nur **4094** VLANs)                                              |