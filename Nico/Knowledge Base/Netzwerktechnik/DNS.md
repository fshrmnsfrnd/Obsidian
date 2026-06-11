---
Fach: "[[Berufsschule]]"
Thema:
  - "[[Networks]]"
---
**DNS** oder auch **D**omain **N**ame **S**ystem ist eine **riesige** Weltweit verteilte Datenbank welches Domain-Namen in IP-Adressen auflöst. Diese Datenbank Teile liegen auf so genannten Nameservern. Die Wurzel _(engl.: root)_ sind derzeit 13 Root-Nameserver (A-M), die die Informationen über die **TLD**s (**T**op **L**evel **D**omains) oder auch **FLD**s (**F**irst **L**evel **D**omain) verwalten. Diese TLDs werden von der **ICANN** (Internet Corporation for Assigned Names and Numbers) verwaltet. DNS verwendet das gleichnamige Protokoll DNS.

![[FN4ACnl_eJ-700.webp]]
# Dynamisches DNS
---
![[HPq8EEMau--700.webp]]
# Aufbau
---
Das DNS ist **hierarchisch** aufgebaut. Das bedeutet, das die Struktur von den Root-Serven aus immer mehr nach unten aufgefächert ist.  
![[1DmV8YGo3--700.webp]]

**Hostname + DNS-Suffix = FQDN** (**F**ull **Q**ualified **D**omain **N**ame)

| **Hostname** | **.** | **DNS-Suffix**                       |
| ------------ | ----- | ------------------------------------ |
| www          | .     | [google.com](https://google.com/)    |
| eu           | .     | [store.ui.com](http://store.ui.com/) |
## Zonen
Eine **Zone** ist ein Verwaltungs(teil)bereich im DNS-Namensraum. In der Regel beinhaltet eine Zone genau eine Domäne. (z. B. [bsinfo.eu](http://bsinfo.eu/))  
In dieser Zonen gibt es Datenbankeinträge welche die IP zu einem FQDN auflösen (**Reverse-Lookup Zonendatei**) oder eine FQDN zu einer IP (**Forward-Lookup Zonendatei**).  
**-> ZWEI SEPERATE DATENBANKEN**
## DNS-Records

|**Record**|**Name**|**Beschreibung**|
|---|---|---|
|SOA|Source of Authority|enthält technische Angaben für die gesamte Zone|
|NS|Name Server|verweist auf die Nameserver einer Zone|
|A|Address|Verknüpft einen Domainnamen mit einer IPv4-Adresse|
|AAAA|Address|Verknüpft einen Domainnamen mit einer IPv6-Adresse|
|PTR|Pointer|Verknüpft eine IP-Adresse mit einem Domainnamen|
|CNAME|Canonical Name|Definiert einen Domain namen als Alias für eine anderen|
|MX|Mail Exchanger|Verweist auf einen Mailserver für die Domain|
|TXT|Text|enthalten beliebige alphanumerische Informationen|

# Funktionsweise
---
## Zonenübertragung
Oft werden mehrere DNS-Server aus Redundanz-Gründen gleichzeitig verwendet. Dabei gibt es immer einen **Primären DNS-Server** und einen oder mehrere **Sekundäre DNS-Server**. Die Sekundären DNS-Server haben nur lese rechte und können **keine Einträge** vornehmen. Der Primäre hingegen schon.  
Die Daten werden daher von dem Primären zu dem Sekundären mittels einer **Zonenübertragung** kopiert.  

![[7p_hqA-HOL-700.webp]]
**Vorteile**:
- Ausfallsicherheit (Redundanz)
- Lastverteilung zwischen den Servern
- Entlastung der WAN-Strecke zwischen Standorten
## Zonendelegierung
Bei der **Zonendelegierung** wird die Verwaltung von einer "untergeordnete" Zone an einen anderen Nameserver weiter gegeben.  
![[sOQHHUuf3n-700.webp]]
**Vorteile**
- Aufteilung der DNS-Datenbank (Lastverteilung)
- Entlastung der WAN-Strecke
## Iterative Abfrage
![[AfnAxtsQgV-700.webp]]