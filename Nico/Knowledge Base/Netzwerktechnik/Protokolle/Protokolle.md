---
Fach: "[[Berufsschule]]"
Thema:
  - "[[Networks]]"
---
# Netzzugangs-Ebene
---
## ICMP
**ICMP** steht für **I**nternet **C**ontrol **M**essage **P**rotocol und ist das Protokoll, welches sich um Pings kümmert. Wenn dieses Protokoll also in einer [[Firewall]] z. B. geblockt wird, kann der entsprechende Rechner nicht mehr gepingt werden.
## IP
**IP** steht für **I**nternet **P**rotokoll und ist das Protokoll, welches mit IP-Adressen arbeitet.
# Transport-Ebene
Nun wird genauer auf die Transport-Ebene im OSI-Modell und dessen Protokolle eingegangen.
## TCP
**TCP** steht für **T**ransmission **C**ontrol **P**rotocol und ist ein verbindungsorientiertes (=> benötigt ein Verbindungsaufbau) und zuverlässiges Transportprotokoll.
### Vor- und Nachteile

|**Vorteile**|**Nachteile**|
|---|---|
|Fehlerkorrektur|langsam (bei heutiger Geschwindigkeit **fast** zu vernachlässigen)|
|Flusskontrolle||
|Übermittlung von Status Informationen||
Auf Grund dieser Vor- und Nachteile wird TCP zur Übertragung von Daten hergenommen die **unbedingt** vollständig und richtig sein müssen.  
Beispiele:
- Websites
- Chats
- Downloads von Dateien
- ...
### Verbindungsaufbau
Der Verbindungsaufbau bei TCP erfolgt in drei Schritten.
1. Anfrage von Client:
    - SYN-Flag
    - Sequenznumber (seq) = x
    - Acknowledgenumber (ack) = 0
2. Antwort Server (SYN ACK):
    - SYN- und ACK-Flag
    - Sequenznumber (seq) = y
    - Acknowledgenumber (ack) = x + 1
3. Bestätigung des Clients (ACK):
    - ACK-Flag
    - Sequenznumber (seq) = x + 1
    - Acknowledgenumber (ack) = y + 1

![[Pasted image 20260105173457.png]]

### Verbindungsabbau
Ebenso wie der Verbindungsaufbau muss der Verbindungsabbau in drei Schritten erfolgen.
1. Client oder Server stellt Abbau anfrage:
    - ACK- und FIN-Flag
    - seq = x
    - ack = y
2. Gegenstelle bestätigt den Abbau:
    - FIN- und ACK-Flag
    - seq = y
    - ack = x + 1
3. Client oder Server bestätigen den korrekten abbau:
    - ACK-Flag
    - seq = x + 1
    - ack = y + 1

![[Pasted image 20260105173505.png]]

## UDP
**UDP** steht für **U**ser **D**atagram **P**rotocol und ist im Gegensatz zu TCP ein nicht verbindungsorientiertes Protokoll. (=> benötigt keinen Verbindungsaufbau)

### Vor- und Nachteile
|**Nachteile**|**Vorteile**|
|---|---|
|keine Fehlerkorrektur|schnell|
|keine Flusskontrolle||
|keine Übermittlung von Status Informationen||

Im vergleich zu TCP meint man schnell, dass UDP bestimmt veraltet sei und unnütz, da es so viele Nachteile hat. Jedoch ist UDP immer noch viel in Verwendung und ein wichtiges Protokoll. Z. B. ist es beim Serien-Streamen egal ob in einer Millisekunde ein Pixel falsch angezeigt wird oder fehlt, da man es eh nicht bemerkt.

# Anwendungs-Ebene
---
## Telnet
**Telnet** ist ein Protokoll, das den Remote-Zugang zu einer Shell ermöglicht. Über das gleichnamige Programm "Telnet" kann aber auch die Verbindung zu andren Protokollen Aufgebaut werden.  
Sollte heutzutage **IMMER** deaktiviert werden.
## SSH
**SSH** steht für **S**ecure **Sh**ell und kann ebenso wie Telnet eine Remote-Verbindung zu Shells aufbauen. Im Gegensatz zu Telnet wird hier, wie der Name schon sagt, eine sichere (verschlüsselte) Verbindung zu dem Server aufgebaut. Das verringert die Gefahr des **Sniffings** (Abhören von Informationen/mitlesen) gewaltig.
## SMB
**SMB** oder auch **S**erver **M**essage **B**lock ist ein von Microsoft entwickeltes Protokoll, was zum Datei Austausch über ein Netzwerk dient. Es wird z. B. von Windows-Freigaben verwendet.
## NFS
**NFS** steht für **N**etwork **F**ile **S**ystem und ist für den selben Aufgabenbereich wie SMB zuständig. Es wurde jedoch von Linux entwickelt.
## FTP
**FTP** oder auch **F**ile **T**ransport **P**rotokoll wurde zur einfachen Datenübertragung über Netzwerke entwickelt. Im Gegensatz zur SMB und NFS wird FTP auch über das Internet und nicht nur im Lokalen-Netzwerk verwendet.
## TFTP
Das **T**rivial **F**ile **T**ransfer **P**rotocol, hat viele ähnlich keiten mit FTP. Der größte und entscheidende Unterschied ist, dass TFTP ein **nicht** verbindungsorientiertes Protokoll verwendet, also UDP.
## HTTP
**HTTP** ist ein Protokoll zur Darstellung von Webseiten, es steht für **H**yper**t**ext **T**ransfer **P**rotocol. Dieses Protokoll wird standardmäßig von Browsern benutzt
## HTTPS
**HTTPS** ist das selbe wie HTTP, nur das es noch zusätzlich mit SSL verschlüsselt ist. das "S" bei HTTPS steht für **S**ecure.
## [[DNS]]
**[[DNS]]** ist ein **D**omain **N**ame **S**ystem. Es ist für die Zuordnung der Domain-Namen zur IP-Adressen zuständig.
## SNTP
Das **S**imple **N**etwork **T**ime **P**rotocol (kurz **SNTP**) dient zur Synchronisation der Zeit.
## SNMP
**SNMP** (**S**imple **N**etwork **M**anagement **P**rotocol) dient zur zentralen Verwaltung und Überwachung von Netzwerkelementen (z. B. Server, Drucker, Switche, Computer, Router, ...)
# Ports
---
In diesem Kapitel werden Ports mit den dazu gehörigen Protokollen/Diensten aufgelistet.
## Was ist ein Port?
Ports kann man auch als Türen verstehen, welche zum richtigen Dienst führt.  
Dabei ist aber entscheidend, das auf der OSI-Schicht davor schon das richtige Protokoll gewählt wurde, meist UDP oder TCP .  
![[Pasted image 20260105173514.png]]

Eine **besondere Stellung haben alle Ports von 0 bis 1024**, da diese Offen Dokumentiert sind und jeder nachlesen kann, wie sie funktionieren.

## Port-Liste
---

|Vorheriges Protokoll|Port Nummer|Dienst|
|---|---|---|
|TCP|23|Telnet|
|TCP|22|SSH|
|TCP|445|SMB|
|TCP/UDP|2049|NFSv3|
|UDP|2049|NFSv4|
|TCP|20|FTP-Data|
|TCP|21|FTP-Control|
|UDP|69|TFTP|
|TCP|80|HTTP|
|TCP|443|HTTPS|
|TCP/UDP|53|DNS|
|TCP/UDP|123|SNTP|
|TCP|25|SMTP|
|TCP|110|POP3|
|TCP|143|IMAP|
|UDP|161|SNMP|