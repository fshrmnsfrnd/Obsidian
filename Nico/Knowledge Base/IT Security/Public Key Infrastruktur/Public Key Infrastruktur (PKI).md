---
Fach: "[[ITS]]"
Thema:
  - "[[Security]]"
---
>**PKI** ist ein kryptologisches System zur  
>- Erstellung, Verteilung und Überprüfung digitaler [[Zertifikate]],  
>- die die Authentizität öffentlicher Schlüssel sichern und so Vertraulichkeit und Integrität der Kommunikation gewährleisten.
# Funktionsprinzip
---
- In asymmetrischen Krypto Systemen verschlüsselt der Sender mit dem **öffentlichen Schlüssel** des Empfängers.  
- Damit der Schlüssel echt ist, wird er durch ein **digitales Zertifikat** bestätigt.
## Digitales Zertifikat
- Bestätigt **Authentizität** und **Anwendungsbereich** eines öffentlichen Schlüssels.  
- Geschützt durch eine **digitale Signatur**.  
- Überprüfbar mit dem öffentlichen Schlüssel des Ausstellers.  
## Zertifizierungspfad
- [[Zertifikate]] bilden eine **Kette**, in der jedes Zertifikat das vorherige bestätigt.  
	- Das letzte (Root-Zertifikat) ist **vertrauenswürdig ohne weitere Prüfung**.
- Digitales Zertifikat = Bestätigt Authentizität und Anwendungsbereich eines öffentlichen Schlüssels und ist geschützt durch eine digitale Signatur

# Bestandteile einer PKI
---
## Digitale [[Zertifikate]]  
- Digital signierte Daten zum Nachweis der Echtheit.
## Zertifizierungsstelle (CA, Certificate Authority)  
- Stellt [[Zertifikate]] aus, signiert Anträge und verwaltet ihr eigenes CA-Zertifikat.
## Registrierungsstelle (RA, Registration Authority)
- Prüft und genehmigt Zertifikatsanträge und leitet sie an die CA weiter.
## Zertifikatsperrliste (CRL, Certificate Revocation List)
- Liste widerrufener [[Zertifikate]] (z. B. bei Schlüsselverlust).  
- Wird regelmäßig aktualisiert.  
- Alternative: White-List gültiger [[Zertifikate]].  
- PKI muss eine Statusprüfung anbieten.
## Verzeichnisdienst (DIR, Directory Service)  
- Durchsuchbares Verzeichnis ausgestellter [[Zertifikate]] (z. B. LDAP).
## Time Stamping Service (optional)  
- Erzeugt rechtssichere Zeitstempel für Dokumente oder Transaktionen.
## Validierungsdienst (VA, optional)  
- Echtzeitprüfung von Zertifikaten (z. B. OCSP, SCVP).
# Dokumentation einer PKI
---
- **CP (Certificate Policy):** Anforderungen und Vertrauensbasis der PKI (für Browseranerkennung).  
- **CPS (Certification Practice Statement):** Umsetzung der CP, technische & organisatorische Details.  
- **PDS (Policy Disclosure Statement):** Öffentlicher Auszug aus dem CPS, falls CPS nicht komplett veröffentlicht wird.
# Ziel der PKI
---
Sichere, überprüfbare und vertrauenswürdige Verwaltung digitaler Identitäten und Schlüssel.
![[Pasted image 20251111164211.png]]

# PKI-enabled Application (PKA)
---
Anwendung, die PKI-Sicherheitsdienste nutzt für:  
- Authentisierung  
- Verschlüsselung  
- Digitale Signatur  
# Personal Security Environment (PSE)
---
Sammlung sicherheitsrelevanter Daten eines Teilnehmers, z. B.:  
- Schlüsselpaare (privat/öffentlich)  
- Digitale [[Zertifikate]]  
- Weitere Sicherheitsinfos
# PKIs befriedigen [[Sicherheitsbedürfnisse]]
---

| **Bedürfniss**  | **Mechanismus** |
| --------------- | --------------- |
| Authentizität   | Signatur        |
| Integrität      | Signatur        |
| Verbindlichkeit | Signatur        |
| Einmaligkeit    | TimeStamp       |
| Vertraulichkeit | Verschlüsselung |
