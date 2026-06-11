---
Fach: "[[Berufsschule]]"
Thema:
  - "[[Networks]]"
  - "[[Security]]"
---
# Arten
---
## Paket-Filter
Eine **Paket Filter** Firewall filtert Header Informationen von den OSI-Schichten **2 - 4**:
- Source/Destination IP Address
- Source/Destination Port
- Source/Destination MAC Address
## Application Gateway
**Application Gateways** Inspizieren die Kompletten Pakete auf Schadsoftware und unerwünschten Dateien. Ein bekanntes Beispiel ist ein **Proxy**.

Der Benutzer/Server will auf eine Website gehen z. B. [fshrmnsfrnd.github.io](https://fshrmnsfrnd.github.io). Der Rechner Verbindet sich mit dem Proxy und sagt ihm er soll die Verbindung zu [fshrmnsfrnd.github.io](https://fshrmnsfrnd.github.io) aufbauen. Also baut er für mich die Verbindung auf und leitet mir die Informationen weiter. Ungewollte Seiten und/oder Downloads werden dann vom Proxy nicht weiter geleitet.  
![[dYrTKmrnie-700.webp]]
## Next Generation Gateway
Ein **Next Generation Gateway** verbindet das Application Gateway mit dem Paket Filter und fügt noch eine **Anomalie Erkennung** hinzu. 
Es kann erkennen wenn z. B.:
- ein Portscann gemacht wird
- Auf einmal viele Anfragen auf einen Server kommen
- Auf einmal viele Verbindungen Abbreche
- ...