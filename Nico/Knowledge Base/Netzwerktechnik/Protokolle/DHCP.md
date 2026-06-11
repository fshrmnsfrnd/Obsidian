---
Fach:
Thema:
  - "[[Networks]]"
---
>**D**ynamic **H**ost **C**onfiguration **P**rotocol

Auf dem DHCP Server ist ein bestimmter Netzwerkbereich zur Vergabe von IP Adressen konfiguriert. Diesen nennt man Pool.
# Automatische Adressierung
---
- Jeder Host bekommt automatisch eine IP
- IP ist unbegrenzt gültig
- Wenn der Cache nicht gelöscht wird gehen irgendwann die Adressen aus
# Manuelle Adressierung
---
- Ähnlich wie Reservierungen
- Kann auch direkt am Client vergeben werden (Muss dann aber aus dem DHCP Pool genommen werden)
# Dynamische Adressierung
---
- Leases haben eine Lease Time (Ablaufzeit)
	- Bei der hälfte der Lease Time sendet der Client ein Unicast DHCP Discover an den Server, um seine Lease zu verlängern
- Wenn die Zeit abläuft, kann der Server die IP neu vergeben
- Der Client bekommt dann eine neue IP
# DHCP Kommunikationsaufbau
---
![[images_text_DHCP2.webp]]
