---
Fach:
Thema:
  - "[[Networks]]"
---
Genutzter Adressbereich: `169.254.1.0` - `169.254.254.255`
Netzmaske: `255.255.0.0`

# Eigenschaften
---
- private Adressen
	- kein Routen ins Internet
- reserviert
- Rechner können **ohne** Konfiguration vernetzt werden
	- Keine manuelle Config
	- Keine Config über DHCP
# Verfahren der Zuweisung
---
- Beim Start des Rechners wird aus der `MAC` Adresse eine zufällige IP-Adresse aus den o.g. Bereich berechnet.
- Der Rechner überprüft ob die IP Adresse bereits vergeben ist
	- ARP Anfrage an die errechnete IP Adressen mit:
		- Destination: Errechnete IP Adresse
		- Source: `0.0.0.0`
	- Erfolgt innerhalb eines definierten Zeitraums ein `ARP-Reply`, muss die Adresse neu berechnet werden.