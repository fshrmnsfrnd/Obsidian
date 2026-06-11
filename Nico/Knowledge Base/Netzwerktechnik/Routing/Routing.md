---
Fach: "[[Berufsschule]]"
Thema:
  - "[[Networks]]"
---
Beim Routing werden unterschiedliche Netze miteinander verbunden. Für das Routing wird ein Router oder ein Layer-3-Switch benötigt. Der Layer 3 Switch heißt so, weil er im  
OSI-Modell auf der dritten Ebene arbeitet, also mit IP-Adressen.
# Warum muss man Netze verbinden?
---
Um diese Frage klären zu können muss man sich zuerst fragen, warum trenne ich mein Netzwerk in mehrere kleine Netze überhaupt auf?  
Durch das aufteilen der Netze wird eine höhere Sicherheit erreicht. Z. B. wenn ein Angreifer es in ein Netz geschafft hat, hat er es schwerer hat auf die andren Netzwerke zu kommen.

Damit aber Geräte trotz unterschiedlicher Netze jetzt aber Kommunizieren können, z. B. Webserver und Client, muss zwischen den Netzen geroutet werden.

Aus diesen Gründen ist ein solches Netz  
  ![[rDUf4LQieQ-700.webp]]
schlechter als ein solches.  
![[VWw4qyltX1-700.webp]]

# Wie Funktioniert Routing?
---
Damit ein Router richtig routen kann, benötigt er eine Routing Tabelle mit folgendem Aufbau:  
  ![[RDOMeNKOgM-700.webp]]
In dieser Tabelle steht an welcher Schnittstelle welches Netzwerk anliegt und welches Gateway verwendet werden soll.
## Beispiel
![[h5DGLwpseM-700.webp]]
# Verschiedene Arten
Beim Routing gibt es verschiedene Arten, die Statische und Dynamische.  
![[3zryM7i_5y-638.webp]]
Eine Route beinhaltet vier Hauptbestandteile:
• Zieladresse
• Subnetzmaske
• Gateway- oder Schnittstellenadresse
• Routenkosten (routing costs) oder einen metrischer Wert

# Routenarten:
## Direkt verbundene Routen
Mit dem Anschalten eines Routers werden die konfigurierten Schnittstellen aktiviert. Sobald die
Schnittstellen betriebsbereit sind, speichert der Router, die direkt verbundenen lokalen Netzwerkadressen als verbundene Routen in der Routing-Tabelle.
## [[Statisches Routing|Statische Routen]]
Ein Netzwerkadministrator kann manuell eine statische Route für ein bestimmtes Netz konfigurieren. Eine statische Route bleibt solange unverändert, bis sie der Administrator neu konfiguriert.
## [[Dynamisches Routing|Dynamic Routes]]
Dynamische Routen werden automatisch durch Routing-Protokolle erstellt und gepflegt. Routing-
Protokolle tauschen Routing-Informationen mit anderen Routern im Netz aus.
Es gibt verschiedene Routing Protokolle dafür. Man unterteilt sie in Distance Vector (z.B. RIP) und Link State (z.B. OSPF)
## Default-Route
Die Default-Route ist eine Art statische Route, welche den Gateway bestimmt, wenn die Routing-
Tabelle keinen Pfad zum Zielnetz enthält. Es ist normal für Default-Routen, dass sie auf den
nächsten Router im Pfad zum ISP hinführen.
# Routen Aggregationen
---
Das macht **CIDR** (Classless Interdomain Routing) und **VLSM** (Variabel Length of Subnetmask). Ohne wäre IPv4 schon in den 90ern zusammengebrochen.
![[Pasted image 20260416130110.png]]
