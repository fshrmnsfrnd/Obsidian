---
Fach: "[[KNT]]"
Thema:
  - "[[Networks]]"
---
>Für private, mit dem Interne **nicht** direkt verbundene Netze werden 3 Adressbereiche verwendet

# 1. `10.0.0.0/8`
---
Netz: 1
Adressen: $2^{24}$ = 16.777.216

# 2. `172.16.0.0/16`
---
Netze: 16
Adressen pro Netz: $2^{16}$ = 65.536

### alternative Darstellung
`172.16.0.0/12`
Netz: 1
Adressen: 1.048.576
# 3. `192.168.0.0/16`
---
Netz: 1
Adressen: 65.536
### Häufige Anwendung
`192.168.0.0/24` bis `192.168.255.255`
Netze: 256
Adressen pro Netz: 256
# Besondere IP Adressen
---

| CIDR-Adressblock | Adressbereich | Beschreibung |
| --- | --- | --- |
|0.0.0.0/8 |0.0.0.0 bis 0.255.255.255 |Aktuelles Netz (nur als Quelladresse gültig)|
|10.0.0.0/8 |10.0.0.0 bis 10.255.255.255 |Netzwerk für den privaten Gebrauch|
|14.0.0.0/8 |14.0.0.0 bis 14.255.255.255 |Öffentliches Datennetz|
|24.0.0.0/8 |24.0.0.0 bis 24.255.255.255 |Cable Television Networks|
|39.0.0.0/8 |39.0.0.0 bis 39.255.255.255 |Reserviert aber zur Vergabe vorgesehen|
|127.0.0.0/8 |127.0.0.0 bis 127.255.255.255 |Localnet|
|128.0.0.0/16| 128.0.0.0 bis 128.0.255.255 |Reserviert aber zur Vergabe vorgesehen|
|169.254.0.0/16 |169.254.0.0 bis 169.254.255.255 |Zeroconf|
|172.16.0.0/12 |172.16.0.0 bis 172.31.255.255 |Netzwerk für den privaten Gebrauch|
|191.255.0.0/16| 191.255.0.0 bis 191.255.255.255 |Reserviert aber zur Vergabe vorgesehen|
|192.0.0.0/24 |192.0.0.0 bis 192.0.0.255 |Reserviert aber zur Vergabe vorgesehen|
|192.0.2.0/24 |192.0.2.0 bis 192.0.2.255 |Dokumentation und Beispielcode (TEST-NET)|
|192.88.99.0/24 |192.88.99.0 bis 192.88.99.255 |6to4-Anycast-Weiterleitungspräfix|
|192.168.0.0/16 |192.168.0.0 bis 192.168.255.255 |Netzwerk für den privaten Gebrauch|
|198.18.0.0/15 |198.18.0.0 bis 198.19.255.255 |Netz-Benchmark-Tests|
|223.255.255.0/24 |223.255.255.0 bis 223.255.255.255 |Reserviert aber zur Vergabe vorgesehen|
|224.0.0.0/4 |224.0.0.0 bis 239.255.255.255 |Multicasts (früheres Klasse-D-Netz)|
|240.0.0.0/4 |240.0.0.0 bis 255.255.255.255 |Reserviert (früheres Klasse-E-Netz)|
|255.255.255.255 |255.255.255.255 |Broadcast|
