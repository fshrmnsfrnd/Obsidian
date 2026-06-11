---
Fach:
Thema:
  - "[[Networks]]"
---
>**I**nternet **C**ontrol **M**essage **P**rotocol

>Dient zu **Netzwerkdiagnose** und Geräte die ein Problem erkennen, können die Fehlermeldung über ICMP an das Gerät schicken, von dem sie das fehlerhaft Paket erhalten haben
# ICMP Paket
---
![[Pasted image 20260416143005.png]]
# ICMP Typen
---
## Destination Unreachable (Typ 3)
![[Pasted image 20260416143230.png]]
## Source Quench (Typ 4)
Hier ist der Typ immer 0
- Wenn nicht genug Buffer am Router ist
- Wenn es dem Zielhost zu schnell geht
## Redirect (Typ 5)
- Sendet der Router, wenn er eine kürzere route hat, als die vorgegebene
- In Verbindung damit wird einer der folgenden Codes verwendet:
![[Pasted image 20260416145004.png]]
## Time exceeded (Typ 11)
- TTL Wert hat 0 erreicht
![[Pasted image 20260416145215.png]]
## Parameter Problem (Typ 12)
- ICMP Code immer 0
- Kommt wenn ein Fehler im IP Header ist
- Im Feld Pointer ist die Byte Postion des Fehlers eingetragen
## Echo Request/Echo Reply (Typen 0/8)
- Typ ist immer 0
- Der Echo Request des bekannten `ping` Befehls
## Time Stamp Request/Reply (Typen 13/14)
- Typ ist immer 0
- Wird verwendet um 2 Hosts zeitlich zu synchronisieren
## Information Request/Reply (Typen 15/16)
- IP Ziel ist 0.0.0.0
- Damit wird die Netzadresse gefunden, in dem sich der Host befindet
## Address Mask Request/Reply (Typen 17/18)
- Typ ist immer 0
- Damit erfragt ein Host die Subnetzmaske
- Kann an Router oder als Broadcast gesendet werden