---
Fach: "[[Berufsschule]]"
Thema:
  - "[[Networks]]"
---
Ein **VPN** (**V**irtual **P**rivate **N**etwork) ist eine **sichere Verbindung** von Rechnern und Netzwerken über **unsichere Netze**. (z. B. das Internet)  
Die Verbindung wird mittels [[Kryptografie]] vor Abhören (**Vertraulichkeit**) und Manipulation (**Integrität**) geschützt. Zudem kann die **Authentizität** der Kommunikationspartner gewährleistet werden.

![[b0pYT-jbin-700.webp]]
# Arten
---

| **Art**                                  | **Beschreibung/Beispiel**                            | **Modus**       |
| ---------------------------------------- | ---------------------------------------------------- | --------------- |
| Site-to-Site  <br>_(Gateway-to-Gateway)_ | Eine Verbindung von zwei Firmennetzen                | Tunnel-Modus    |
| End-to-Site  <br>_(Host-to-Gateway)_     | Außendienstmitarbeiter greift auf das Firmennetz zu. | Tunnel-Modus    |
| End-to-End  <br>_(Host-to-Host)_         | Ein PC soll genau auf einene Server zugreifen können | Transport-Modus |
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