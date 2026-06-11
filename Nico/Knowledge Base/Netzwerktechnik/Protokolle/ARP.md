---
Fach:
Thema:
  - "[[Networks]]"
---
# Funktionsweise
---
1. PC1 schickt einen `ARP Request` als Layer 2 Broadcast (``FF:FF:FF:FF:FF:FF``) 
2. Alle Geräte die den Broadcast bekommen antworten an die IP von PC1 mit einem `ARP Reply`, der die MAC und IP beinhaltet
3. PC1 speichert sich alle Quell IPs und MACs die er als `ARP Reply` bekommen hat im `ARP Table` 
# Paket
---

| ARP-Nachrichtenformat am Beispiel Ethernet-MAC-Adressen und IPv4-Adressen |                                   |                      |
| ------------------------------------------------------------------------- | --------------------------------- | -------------------- |
| octet offset                                                              | 0                                 | 1                    |
| 0                                                                         | Hardwareadresstyp                 |                      |
| 2                                                                         | Protokolladresstyp                |                      |
| 4                                                                         | Hardwareadressgröße               | Protokolladressgröße |
| 6                                                                         | Operation                         |                      |
| 8                                                                         | Quell-MAC-Adresse (erste 2 Bytes) |                      |
| 10                                                                        | (nächste 2 Bytes)                 |                      |
| 12                                                                        | (letzte 2 Bytes)                  |                      |
| 14                                                                        | Quell-IP-Adresse (erste 2 Bytes)  |                      |
| 16                                                                        | (letzte 2 Bytes)                  |                      |
| 18                                                                        | Ziel-MAC-Adresse (erste 2 Bytes)  |                      |
| 20                                                                        | (nächste 2 Bytes)                 |                      |
| 22                                                                        | (letzte 2 Bytes)                  |                      |
| 24                                                                        | Ziel-IP-Adresse (erste 2 Bytes)   |                      |
| 26                                                                        | (letzte 2 Bytes)                  |                      |

# Arten von ARP
---
### Proxy-ARP
Proxy ARP  ist eine Technik, mit der ein Proxy-Gerät in einem bestimmten Netzwerk die  ARP-Anfrage nach einer IP-Adresse beantwortet , die sich nicht in diesem Netzwerk befindet. Der Proxy kennt den Standort des Ziel des Datenverkehrs und bietet seine eigene  MAC-Adresse  als Ziel an. 
### Gratuitous-ARP
Das Gratuitous-ARP gleicht fast einem administrativen Verfahren, das als eine Möglichkeit für einen Host in einem Netzwerk durchgeführt wird, um seine IP-to-MAC-Adresse bekanntzugeben oder zu aktualisieren. Das Gratuitous-ARP wird nicht durch eine ARP-Anfrage zur Übersetzung einer IP-Adresse in eine MAC-Adresse aufgerufen.
### Reverse-ARP (RARP)
Host-Maschinen, die ihre eigene IP-Adresse nicht kennen, können das Reverse Address Resolution Protocol (RARP) verwenden, um sie herauszufinden.
### Inverse-ARP (IARP)
Während ARP eine IP-Adresse verwendet, um eine MAC-Adresse zu finden, verwendet IARP eine MAC-Adresse, um eine IP-Adresse zu finden.