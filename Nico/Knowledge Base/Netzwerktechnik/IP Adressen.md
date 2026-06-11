---
Fach: "[[Berufsschule]]"
Thema:
  - "[[Networks]]"
---
IP-Adressen sind eindeutige IDs innerhalb **eines** Netzwerkes. Sie werden Entweder Dynamisch (DHCP) oder Statisch (manuell) vergeben. Es gibt sie in zwei formen:
- [[#IPv4]]
- [[#IPv6]]

Zudem definieren IP-Adressen auch Netzwerkbereiche, dies passiert mittels Subnetzmasken.  
Man findet sie auf OSI-Schicht 3.
# Aufbau von IP-Adressen
---
Die folgenden Beispiele gelten für [[#IPv4]] und [[#IPv6]]- Adressen, der einzige Unterschied ist die Schreibweise und Länge der IP-Adressen. Zur leichteren Lesbarkeit werden nun IPv4-Adressen verwendet.

| **Subnetzmaske**                   | **IP-Adresse**                      | **Schreibweise** |
| ---------------------------------- | ----------------------------------- | ---------------- |
| 255.255.255.0                      | 192.168.1.37                        | Decimal          |
| 11111111 11111111 1111111 00000000 | 11000000 10101000 00000001 00100101 | Binär            |

An den stellen, wo die Subnetzmaske die Einser hat ist der sogenannte **Netz-Anteil**, da wo die Nuller sind ist der sogenannte **Host-Anteil**. Der Netz-Anteil darf dann nicht verändert werden. Also wären gültige Adressen von 192.168.1.0 bis 192.168.1.255.  
Eine kürzere Schreibweise ist "Netzadresse/länge" des Netzanteils in Bit.  
**Beispiel** für IPv4:
- 192.168.1.0/24
**Beispiel** für IPv6:
- fe05::1/16

# IPv4
----
**IPv4** (lang **I**nternet **P**rotokoll **V**ersion **4**) kümmert sich darum, dass IP-Adressen (der vierten Version) gefunden werden.
## IPv4 Aufbau
IPv4-Adressen bestehen aus **vier Oktetten**, die in gepunkteter Decimal-Schreibweise dargestellt werden.  
z. B.:

| **Adresse**                         | **Schreibform**                 |
| ----------------------------------- | ------------------------------- |
| 11000000 10101000 00000001 00100101 | Binär                           |
| 192.168.1.37                        | gepunktete Decimal-Schreibweise |
## Besondere Adressen
Broadcast-Adressen sind bei IPv4 immer die letzte IP-Adresse im Netz. Die Netzadresse ist immer die erste Adresse im Netzwerk. Beide Adressen dürfen **NIEMALS** an Clients vergeben werden.

# IPv6
---
**IPv6** steht für _**I**nternet **P**rotokoll **V**ersion **6**_. IPv6 wurde Entwickelt, weil die IPv4 Adressen ausgegangen sind. IPv4 hat 2³² und IPv6 hat 2¹²⁸ mögliche Adressen. Daran sieht man, dass IPv6 einen viel größeren Adressbereich hat als IPv4.  
Beispiele:
- IPv4: 192.169.0.12
- IPv6: fe80:f890::1
## IPv6 Adressraum
IPv6 hat 128 bit, die in Doppelpunkt-Schreibweise in Hexadezimalen Zahlen dargestellt werden, also Zahlen von 0 - f.

![[4DK_s6VvwO-659.webp]]
## Verkürzungs Regeln
Es gibt zwei verschiedene Verkürzungs Regeln, mit denen man IPv6 Adressen abkürzen kann. In den Folgenden Kapiteln, wird jeweils nur eine Regel aus veranschaulichungs Gründen angewandt. Natürlich können die Regeln kombiniert werden.
### Vornullen
Pro Block können sämtliche Vornullen weggelassen werden z. B.:

| 2001:0db8:0000:08d3:0000:8a2e:0070:7344 | vorher  |
| --------------------------------------- | ------- |
| 2001:db8:0:8d3:0:8a2e:70:7344           | nachher |
### Nullerblöcke
Es können Nuller Blöcke oder Nuller Blöcke Reihen durch "::" ersetzt werden. Diese Regel kann jedoch aus eindeutigkeits Gründen nur einmal angewandt werden. z. B.:

| 2001:0000:0000:1db8:0000:0000:0000:1428 | Vorher  |
| --------------------------------------- | ------- |
| 2001::1db8:0000:0000:0000:1428          | Nachher |
| 2001:0000:0000:1db8::1428               | Nachher |
## Besondere Adressen
  ![[9F-lgE49OI-700.webp]]
![[bBdzOdyxAj-700.webp]]
- Unicast: Geht an genau ein Node
    - Global Unicast: Globale IP-Adresse (vom Internet Erreichbar)
    - Link-Locale IP-Adresse (wird nicht geroutet)
- Multicast: Geht an mehrer Nodes
- Anycast: Geht an eine vordefinierte Gruppe an Nodes (es muss nur einer Antworten)
_**(Bei IPv6 nennt man Geräte Nodes)**_

![[SQuj1OtOVe-700.webp]]
## SLAAC
**SLAAC** oder auch **S**tate**l**ess **A**ddress **A**uto**c**onfiguration dient zur selbstständigen konfiguration einer **Unique-Local-Scope** Adresse.

Der Router schickt dafür in regelmäßigen Abständen z. B. alle 30 Sekunden ein**Router Advertisement** an die Addresse **FF02::2** (Multicast für alle Nodes). In diesem Advertisement stehen Informationen wie den **on-Link-Präfix**. Mit Hilfe dieses Präfix erstellt sich der Client dann seinen**Interface Identifier**.  
Falls der Client aber den Router Advertisement verpasst, kann er diesen über eine **Router Solicitation** anfordern 1 = Multicast für alle Router.

![[aOS0GC9Xqf-645.webp]]

## Vor- und Nachteile von IPv6
### Vorteile
- Automatische Konfiguration (DHCP evtl. unnötig)
- Multicast durch spezielle Adressen
- schnelleres [[Routing]]
- Punkt-zu-Punkt-Verschlüsselung
- Datenpakete bis 4 GByte (Jumbograms)
- einfache Header Erweiterung  
    ![[XAa7rNxf0S-518.webp]]
- neue [[Protokolle]]
    - NPM (Neighbour Discovery Protokoll)
    - ICMPv6 (Fehlerbehandlung)

### Nachteile
- Nicht alle Geräte und Anwendungen unterstützen IPv6
- Übergangstechnologien verhindern eine schnelle Einführung
- hohe Komplexität (Schulungsbedarf)
- fehlende Anonymität bei SLAAC (Autokonfiguration) wegen Verarbeitung der MAC-Adresse (Behoben durch IPv6 Privacy Extenstion)
- automatische Namensvergabe (über [[DNS]]) ist ein IPv6-DHCP-Server nötig