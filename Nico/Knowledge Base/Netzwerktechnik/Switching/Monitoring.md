---
Fach:
Thema:
  - "[[Knowledge Base/Netzwerktechnik/Switching/Switching|Switching]]"
---
# SNMP
---
**S**imple **N**etwork **M**anagement **P**rotocol dient in größeren Netzen zur **zentralen** Überwachung von Servern, Switches, Routern oder WLAN-Basisstationen. Die SNMP-Versionen 1 und 2c bieten nur grundlegenden Zugriffsschutz, erst SNMPv3 ermöglicht sichere Authentifizierung. Mit SNMP kann der Admin den **Status** (etwa Up/Down, Paket- und Fehlerzähler) von Ports abfragen und teils auch **Konfigurationen** machen.
## RMON
**R**emote **Mon**itoring ist eine **Erweiterung** von SNMP. Es liefert wie dieses vorrangig **statistische Informationen**, kann aber je nach Implementierung auch Frames analysieren und sammeln.
# Port Mirroring
---
Port Mirroring leitet bei Switches den Verkehr von einem, manchmal auch mehreren Anschlüssen an einen **Monitor-Port** weiter, an den der Admin seinen **Diagnose**-PC anschließen kann. 

>[!Warning] 
>Weil man damit auch Anwenderdaten und Passwörter zu Gesicht bekommt, ist es aus **Datenschutzgründen** unerlässlich, dass der Switch dem Admin nur per Passwort Zugriff gewährt. Daraus resultiert auch die Pflicht, den neuen Switch schon **vor dem Einbau** ins LAN zu **konfigurieren** und ein eigenes Passwort zu setzen. Sonst könnte sich ein beliebiger Mitarbeiter Port Mirroring auf seinen Anschluss schalten.

Der Monitor Port wird auch Mirror Port, **SPAN** (Switch Port Analyser) Port oder **Maintenance Port** bezeichnet. Allerdings werden bei fast allen Herstellern **nicht alle Frames** zum Monitor Port gespiegelt. Defekte Frames werden nicht an den Monitor Port übertragen. Oft werden auch nur die Frames eines VLANs gespiegelt. Und bei einer Fullduplex-Verbindung können nur 100 Mbit/s am Monitor Port ankommen obwohl ja 200 Mbit/s möglich sind. Die Ports müssen im selben [[VLAN]] sein und der Monitor Port muss genug Bandbreite haben

**Konfigurationsbeispiel:**
```ciscoCLI
conf t 
int gi0/7 ! auf diesen Port (gi0/7) kommt der Sniffer port 
monitor gi0/2 ! und dieser Port (gi0/2) wird gespiegelt 
end 

! Zur Kontrolle dient das Kommando 
show port monitor ! und deaktiviert wird der Spiegelport mit: 
conf t 
int gi0/7 
no port monitor 
end
```
