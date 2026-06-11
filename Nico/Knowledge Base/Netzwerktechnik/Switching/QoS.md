---
Fach:
Thema:
  - "[[Knowledge Base/Netzwerktechnik/Switching/Switching|Switching]]"
---
**Q**uality **o**f **S**ervice ordnet Frames eine **Dringlichkeit** zu, z.B. für VoiP oder Streaming. 
Die 3 Bits im QoS Tag erlauben 8 Dringlichkeitsstufen, diese werden vom Switch in verschieden Queues abgebildet.

Die Zuordnung geschieht wie beim VLAN: 
- abhängig vom Port, dem man in der Switch-Konfiguration eine feste Stufe zuordnet (port-based)
- der Switch übernimmt das Tag aus dem hereinkommenden Paket (802.1p).

# Weiterleitungsstrategien für QoS
#### Strict Queueing
Stehen in der Queue mit der höchsten Priorität Daten an, so leitet der Switch diese bevorzugt weiter. Erst wenn die Daten der höchsten Queue komplett abgearbeitet sind, ist die nächst niedrigere Queue dran.
>Dabei kann passieren, dass die niedrigste Priorität viel zu selten an die Reihe kommt.
#### (Weighted) Round Robin
Das Rundlaufverfahren (engl. *Round Robin*) gibt allen Elementen einer begrenzten Gruppe gleichmäßig und in einer bestimmten Abfolge Zugriff auf eine Ressource. Stellt sicher dass auch niedrige Prioritäten (seltener) durchkommen.
#### DiffServ
**Diff**erentiated **Serv**ices arbeitet auf **Layer 3**.
Er nutzt im IP-Header das 6 Bit lange Type-of-Service-Feld (**ToS**) für Dienstklassen; RFC 2474 definiert 64 verschiedene, und die auf den Ethernet-Geräten laufenden Anwendungen stufen ihre Daten selbst ein. Die Switches müssen die 64 ToS Klassen dann auf ihre acht Stufen abbilden.

> [!Warning] QoS im Ethernet
> Es gibt bei Ethernet wegen des zufälligen Medienzugriffs prinzipiell keine Dienstgütegarantie, man spricht deshalb eher von **C**lass **o**f **S**ervice, kurz **CoS**.
