---
Fach:
Thema:
  - "[[Networks]]"
---
>Routingprotokolle erstellen und verteilen automatisch Routingtabellen, und finden Routen zwischen Netzen

# Distance Vector Protokols
---
> Router teilen ihren direkten Nachbarn ihre Routing Tabelle mit
## RIP(v2)
>**R**outing **I**nformation **P**rotocol
- Sendet alle 30 sek seine Routing Tabelle an alle direkten Nachbarn 
- Sucht die kürzeste Anzahl Hops
- Max. 15 Hops, sonst wird der Eintrag nicht gespeichert
- lange Konvergenzzeit
### Konvergenzzeit
>Es dauert sehr lange bis alle Router alle Routen gelernt haben.

Es gibt Methoden, diese zu verkürzen:
#### Split Horizon
Die Router verbreiten die Routen nicht zurück an den Router, von dem sie sie gelernt haben.
#### Split Horizon mit Poison Reverse
Wie Split Horizon, nur dass, statt die Routen nicht zu senden, die Routen mit 16 Hops Entfernung gesendet werden, und dadurch erst beim empfangenden Router verworfen werden.
#### Triggered Updates
Die Router warten nicht die 30 Sekunden ab, sondern senden, sobald sie Änderungen haben.
## IGRP
>**I**nterior **G**ateway **R**outing **P**rotocol
- Cisco‑proprietär (klassisches IGP, heute praktisch abgelöst)
- Metrik basiert auf mehreren Faktoren (statt nur Hop‑Count), typischerweise:
	- Bandbreite
	- Verzögerung (Delay)
	- Zuverlässigkeit (Reliability)
	- Auslastung (Load)
	- MTU (wird i.d.R. nicht in die Berechnung einbezogen)
- **Max. Hop Count** standardmäßig **100** (konfigurierbar bis **255**)
- Unterstützt **Classful Routing** (keine VLSM/CIDR-Unterstützung) → kann bei Subnetting schnell zum Problem werden
- **Konvergenz** besser als RIP, aber im Vergleich zu modernen Protokollen eher langsam
- Mechanismen zur Stabilisierung:
- **Hold‑Down Timer** (verhindert „Flapping“/Routing‑Schleifen)
- **Route Poisoning** (ungültige Routen „vergiften“)

## Enhanced IGRP
>Enhanced **I**nterior **G**ateway **R**outing **P**rotocol
- Cisco‑proprietär, modernes Nachfolgeprotokoll von IGRP
- „Advanced Distance Vector“ (häufig als Hybrid bezeichnet)
- Verwendet den **DUAL‑Algorithmus** (Diffusing Update Algorithm) für schnelle, loop‑freie Berechnung
### Eigenschaften / Funktionsweise
- **Schnelle Konvergenz** (oft deutlich schneller als RIP/IGRP)
- Sendet **keine kompletten Tabellen periodisch**, sondern:
	- **Hello‑Pakete** zum Nachbarn finden/halten
	- **Triggered Updates** (nur bei Änderungen relevante Infos)
- Arbeitet mit **Neighbor Tables**, **Topology Table** und **Routing Table**
- Unterstützt **VLSM/CIDR** (classless)
- Unterstützt **Summarization** (Routen zusammenfassen), sinnvoll zur Reduktion von Tabellen/Updates
### Metrik
- Kombiniert standardmäßig:
	- Bandbreite (Bandwidth)
	- Delay
- Optional (über K‑Werte) zusätzlich:
	- Reliability
	- Load
	-  MTU (wird i.d.R. nicht gerechnet)
### Weitere wichtige Begriffe
- **Feasible Successor**: „Backup‑Route“, die sofort einspringen kann (schneller Failover)
- **Feasibility Condition**: Bedingung, damit eine Route als loop‑frei gilt

## BGP
>**B**order **G**ateway **P**rotocol
- Wird hauptsächlich für Routing **zwischen autonomen Systemen (AS)** genutzt (Internet‑Backbone), kann aber auch intern genutzt werden (**iBGP**)
### Grundprinzip
- BGP entscheidet nicht „kürzester Weg“, sondern **Policy‑basiert** („Welche Route will ich bevorzugen/erlauben?“)
- **Loop‑Vermeidung** u.a. über **AS‑Path** (wenn eigene AS‑Nummer im Pfad vorkommt → Route verwerfen)
### Sessions / Betrieb
- Baut Nachbarschaften als **TCP‑Session (Port 179)** auf (kein Broadcast/Multicast wie z.B. OSPF)
- BGP sendet Updates **ereignisbasiert** (nicht alle 30s komplette Tabellen)
- Nutzt **Keepalive** und **Hold Timer** zur Nachbarüberwachung
### Wichtige Attribute (für die Routenwahl)
- **AS‑Path**: „Pfadlänge“ über AS hinweg (kürzer meist bevorzugt)
- **Local Preference**: interne Bevorzugung von Ausgängen (höher = besser)
- **MED** (Multi Exit Discriminator): Empfehlung, welchen Eingang der Nachbar nutzen soll (niedriger = besser)
- **Next Hop**: nächster Hop, muss erreichbar sein (sonst Route nicht nutzbar)
# Link State Protokols
---
>Zentrale Datenbank, eignet sich sehr gut für große Netze

- Das Netz wird in logische Bereiche aufgeteilt (Areas)
- Die Netzwerkstruktur wird in einer Link Status Datenbank gespeichert
- Router in einer Area haben die selbe Datenbank
- Router berechnen die beste Route aufgrund der Datenbank
## OSPF
>**O**pen **S**hortest **P**ath **F**irst
- Die Router finden sich über Multicast (224.0.0.5) Dadurch ist weniger Traffic
- Die Router handeln einen **DR** (Designated Router) und einen **BDR** (Backup Designated Router) aus
- Der DR steuert das gesamte Netz
- Es werden Areas unter direkt verbundenen **Internal Routers** gebildet
- Die Router senden regelmäßig **LSA**s (Link State Advertisements), mit Infos über den Routerzustand
- Internal Routers verwenden eine Datenbank, **Area Border** Routers verwalten 3 Datenbanken