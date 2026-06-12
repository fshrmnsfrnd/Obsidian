---
Fach:
Thema:
  - "[[Security]]"
---
https://nmap.org/

# Ziele
- Alle im Netzwerk aktiven Komponenten aufspüren
- Offene Ports auf den einzelnen Systemen finden und dokumentieren
- Auf den Systemen laufende Dienste identifizieren und dokumentieren
- Schwachstellen auf den Systemen finden

Nmap ist ein viel genutzter Portscanner mit umfangreichen Möglichkeiten. Wie fast alle Scanning Tools ist nmap ein Kommandozeilentool. Zenmap ist eine grafische Oberfläche zu nmap.
# Kurzübersicht
| Befehl                                   | Zweck                                                       |
| ---------------------------------------- | ----------------------------------------------------------- |
| ``nmap 192.168.1.2``                     | Einfacher Scan eines Hosts (wichtige TCP-Ports)             |
| ``nmap 192.168.1.0/24``                  | Scan des gesamten /24-Netzes (Host-Discovery + Ports)       |
| ``nmap -T4 -sV 192.168.1.2``             | Schneller Scan mit Service-/Versions-Erkennung              |
| ``nmap -A -T5 -v 192.168.1.2``           | Aggressiver Detailscan (OS, Versionen, Skripte, Traceroute) |
| ``nmap -p 80,443 192.168.1.2``           | Nur bestimmte Ports scannen                                 |
| ``nmap -p- 192.168.1.2``                 | Alle Ports (1–65535) scannen                                |
| ``nmap -sS 192.168.1.2``                 | SYN-Scan (schnell, „stealth“)                               |
| ``nmap -sU -p 53,123 192.168.1.2``       | UDP-Scan (z.B. DNS, NTP)                                    |
| ``nmap -O 192.168.1.2``                  | Betriebssystem-Erkennung                                    |
| ``nmap -sC -sV 192.168.1.2``             | Standardskripte + Versionsscan                              |
| ``nmap --script=vuln 192.168.1.2``       | Schwachstellen-Skripte ausführen                            |
| ``nmap -A -T4 -oN scan.txt 192.168.1.2`` | Aggressiver Scan, Ausgabe in Datei speichern                |
# Grundprinzip
Zweck: Scan von Hosts und Ports im Netzwerk (Welche Geräte? Welche Dienste? Welche Versionen?
**Standardbefehl**  `nmap <Ziel>`  Ziel kann IP, IP-Bereich oder Hostname sein
# Einfache Scans
**Einzelnen Host** scannen  
`nmap 192.168.1.2`  
Erkennt: offene Ports (Standard: nur wichtigste TCP-Ports)

**Ganzes Netz** scannen  
`nmap 192.168.1.0/24`  
Erkennt: welche Hosts im Netz sind + deren offene Standard-Ports
# Häufig genutzte Optionen
### Schnellerer Scan (Aggressivität/Timing)  
`-T0` bis `-T5` (0 = sehr langsam, 5 = sehr aggressiv)  
### Service-/Versionsscan  
 `-sV`  
Erkennt Versionen der Dienste (z.B. Apache 2.4.54, OpenSSH 8.9)
### Aggressiver Scan (Fingerprinting)  
`-A`  
Enthält u.a.: `-sV`, OS-Erkennung, Traceroute, Skripte  
Nutzt du in: `nmap -A -T5 -v 192.168.1.2`
### Verbose-Ausgabe  
`-v` bzw. `-vv`  
Mehr Details während und nach dem Scan
### Beispiele:
`nmap -T4 -sV 192.168.1.2`
`nmap -A -T5 -v 192.168.1.2`
# Weitere oft genutzte, praktische Optionen
## Port-Auswahl
Bestimmte Ports:
`-p 22,80,443` (nur diese)
Portbereich:
`-p 1-1000`
Alle Ports:
`-p-` (1–65535)

Beispiele:
- `nmap -p 80,443 192.168.1.2`
- `nmap -p- 192.168.1.2`
## Scan-Arten
- TCP-Connect-Scan (Standard ohne Root/Admin):
	- `-sT`
- SYN-Scan (schnell/„stealth“, meist Standard mit Root/Admin):
	- `-sS`
- UDP-Scan:
	- `-sU`
Beispiele:
- `nmap -sS 192.168.1.2`
- `nmap -sU -p 53,123 192.168.1.2`
## Betriebssystem-Erkennung
- OS-Fingerprinting:
	- `-O`
- Beispiel:
	- `nmap -O 192.168.1.2`
## Nmap-Skripte (NSE)
- Skript-Engine:
	 - `-sC` (Standardskripte)
	- `--script=<name oder kategorie>`
- Beispiele:
	- `nmap -sC -sV 192.168.1.2`
	- `nmap --script=vuln 192.168.1.2`
## Output / Speicherung
- Normale Ausgabe in Datei:
	- `-oN scan.txt`
- Grep-freundlich:
	- `-oG scan.gnmap`
- XML (für Tools):
	- `-oX scan.xml`

Beispiel:
- `nmap -A -T4 -oN scan_192.168.1.2.txt 192.168.1.2`
## Typische Praxis-Kombis
- Schneller Überblick über ein Netz:
	- `nmap -T4 192.168.1.0/24`
- Detailcheck eines Hosts:
	- `nmap -A -T4 -p- 192.168.1.2`
- Versionen + Standardports:
	- `nmap -T4 -sV 192.168.1.2`  ← aus deiner Notiz
- Aggressiver Hostscan mit viel Info:
	- `nmap -A -T5 -v 192.168.1.2`  ← aus deiner Notiz