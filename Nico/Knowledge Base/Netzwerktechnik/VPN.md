---
Fach:
Thema:
  - "[[Networks]]"
---
# Was ist ein VPN?
---
>Ein **V**irtual **P**rivate **N**etwork ist ein logisches privates Netzwerk welches es ermöglicht über die **öffentliche** Infrastruktur (Internet, MPLS(**M**ulti **P**rotocol **L**abel **S**witching)) mit anderen Geräten zu kommunizieren. 

Ein bekannter Anwendungsfall ist zum Beispiel das Homeoffice. Es wird eine VPN verwendet um über das Internet (öffentliche Infrastruktur) sicher mit dem LAN der Firma zu kommunizieren.  

In diesen VPNs gelten die gleichen Sicherheits- und Verwaltungsrichtlinien wie in einem privaten Netz.  

**TLDR:** Ein VPN ist eine **kostengünstige** Möglichkeit eine **Point-to-Point** Verbindung über **öffentliche Infrastruktur** wie z. B. das Internet auf zu bauen.

# VPN Typen
---
![[b0pYT-jbin-700.webp]]

| **Art**                                  | **Beschreibung/Beispiel**                            | **Modus**       |
| ---------------------------------------- | ---------------------------------------------------- | --------------- |
| Site-to-Site  <br>_(Gateway-to-Gateway)_ | Eine Verbindung von zwei Firmennetzen                | Tunnel-Modus    |
| End-to-Site  <br>_(Host-to-Gateway)_     | Außendienstmitarbeiter greift auf das Firmennetz zu. | Tunnel-Modus    |
| End-to-End  <br>_(Host-to-Host)_         | Ein PC soll genau auf einene Server zugreifen können | Transport-Modus |
# Funktionsweise
---
Bei VPNs werden die Datenpakete verschlüsselt und dann erst über die öffentliche Infrastruktur gesendet. Diese Verschlüsselung nennt man bei VPNs auch **Tunneling** oder **Kapselung**, da das ganze logisch so aussieht als ob die Daten durch einen Tunnel geschickt werden bzw. noch mal in eine Kapsel gesteckt werden.
# Protokolle
---

| OSI-Schicht | Beispiele                                                                                                                                                        |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 4-7         | - Secure Socket Layer/Transport Layer Security (SSL/TLS) z. B. bei HTTPS  <br>- Micorosoft SSTP-VPN (Secure Socket Tunneling Protokol)  <br>- SSH  <br>- OpenVPN |
| 3           | - IP Security (IPSec)                                                                                                                                            |
| 2           | - Point-to-Point Tunneling Protocol (PPTP)  <br>- Layer 2 Tunneling Protocol (L2TP)                                                                              |
## IPSec
**IP Security** (**IP Sec**urity) ist eine Sammlung von Protokollen zur Absicherung des **IP-basiertem Netzverkehr**:
- **Authentication Header (AH)**:  
    Sorgt für **Authentizität** und **Integrität** der übertragenen Daten. AH stellt dies über eine **Digitale Signatur** sicher. AH verschlüsselt **NICHT!**  
    AH funktioniert oft mit NAT **NICHT** weil dort die IP-Adresse ändert und somit die Signatur nicht mehr stimmt.
- **Encapsulating Security Payload (ESP)**:  
    Sorgt für **Vertraulichkeit** der übertragenen Daten. (**Versclüsselung**)
- **Internet Key Exchange (IKE)**:  
    Über dieses Protokoll werden die Schlüssel für AH bzw. ESP erzeugt, verwaltet und der Kommunikationspartner authentifiziert.
# Vorteile von VPNs
---
Wichtige Vorteile die VPNs mit sich bringen sind:  
- Ermöglichung von sicheren Fernzugriff  
- Schutz der Daten vor Mitlesen (Tunneling)  
- öffentliche Infrastruktur kann verwendet werden

