---
Fach:
Thema:
  - "[[Networks]]"
---
Beim Statischen Routing wird die Routing Tabelle von Hand gepflegt.
In der Routing Tabelle sind Remote Netzwerke (nicht direkt verbundene Netze) und der Next Hop dahin gespeichert.
Eine Routing Tabelle ist immer wie folgt aufgebaut:

| Destination   | Subnet Mask    | Port                           | Gateway                           |
| ------------- | -------------- | ------------------------------ | --------------------------------- |
| 192.168.3.0   | 255.255.255.0  | ETH1                           | 192.168.2.1                       |
| `Netzadresse` | `Subnetzmaske` | `Schnittstelle an sich selbst` | `Next Hop (Direkt angeschlossen)` |
| 0.0.0.0       | 0.0.0.0        | ETH0                           | 172.10.0.1                        |
`0.0.0.0` ist das Standard Gateway, wenn das Ziel unbekannt ist (geht typischerweise ins Internet).
