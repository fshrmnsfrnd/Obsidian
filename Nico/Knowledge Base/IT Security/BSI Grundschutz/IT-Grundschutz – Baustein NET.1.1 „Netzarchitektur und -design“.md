---
Thema:
  - "[[BSI Grundschutz]]"
Fach:
---
## 1. Gliederung des Bausteins NET.1.1
1. **Beschreibung**  
	- Zielsetzung
		- Informationssicherheit als integralen Bestandteil der Netzarchitektur und des Netzdesigns
	- Abgrenzung und Modellierung
		- Netzwerkkomponenten selbst sind hier nicht geregelt
		- Funktechniken und Netzbereiche (LAN, WLAN, WAN,...) sind hier nicht geregelt
2. **Gefährdungslage**
	- Ausfall oder unzureichende Performance von Kommunikationsverbindungen
	- Ungenügend abgesicherte Netzzugänge
	- Unsachgemäßer Aufbau von Netzen
3. **Anforderungen**
	- Basisanforderungen
	- Standardanforderungen
	- Anforderungen bei erhöhtem Schutzbedarf
4. **Weiterführende Informationen**

---
## 2. Bedeutung der Schlüsselbegriffe
Diese Begriffe legen den **Verbindlichkeitsgrad** fest:
- **MUSS**  (Basis Schutz)
    Zwingend umzusetzen. Keine Ausnahme zulässig. Nicht umgesetzt = Grundschutz nicht erfüllt.
- **DARF NUR**  (Basis Schutz)
    Ausschließlich unter den genannten Bedingungen erlaubt.
- **DARF NICHT / DARF KEIN** (Basis Schutz) 
    Striktes Verbot.
- **SOLLTE**  (Standard/Hoher Schutz)
    Starke Empfehlung. Abweichung nur mit nachvollziehbarer Begründung.
- **SOLLTE NICHT / SOLLTE KEIN**  (Standard/Hoher Schutz)
    Klare Negativempfehlung, Abweichung nur in Ausnahmefällen.
**MUSS = Pflicht**, **SOLLTE = dringend empfohlen**.

---
## 3. Mögliche Gefährdungen (Auswahl + Beispiel)
Typische Gefährdungen in NET.1.1:
- Unklare oder gewachsene **Netzstrukturen**
- Fehlende **Netzsegmentierung**
- Ungesicherte **Netzzugänge**
### Beispiel:
Ein Unternehmen betreibt ein **flaches Netzwerk**, in dem:
- Clients
- Server
- Drucker und
- Administrationssysteme  
im selben Netzsegment liegen.

➡️ Wird ein einzelner Client durch Malware kompromittiert, kann sich der Angreifer seitlich im gesamten Netz bewegen (z. B. Zugriff auf Server).

---
# 4. Umsetzungshinweise
Ja, überwiegend **praxisnah und sinnvoll**, aber:
- Sie sagen **nicht**, _was genau_ technisch zu konfigurieren ist
- Sie geben **keine Schritt-für-Schritt-Anleitung**
- Sie setzen **Grundwissen in Netzwerktechnik** voraus
### Beispiele:
- Aufbau einer **Zonenarchitektur** (z. B. internes Netz, DMZ, externes Netz)
- Trennung von Netzen durch Firewalls oder Router
- **Dokumentation** der Netzstruktur

➡️ Für Planung und Bewertung hilfreich, für technische Umsetzung braucht man zusätzliche Fachkenntnis.

---
# 5. Anforderungen

### Basisanforderungen

NET.1.1.A1 Sicherheitsrichtlinie für das Netz (B)
- spezifische Sicherheitsrichtlinie
	- Segmentierung
	- Netzwerktrennung
	- Welche Netzwerkübergänge erlaubt sind
	- Administration und Überwachung trennen
	- Standortübergreifende Kommunikation
	- Institutionsübergreifende Kommunikation
- nachvollziehbare Anforderungen und Vorgaben
- Richtlinie bekannt an Mitarbeiter
- Dokumentieren von Änderungen
- Regelmäßige Prüfung der Richtlinie

NET.1.1.A2 Dokumentation des Netzes (B)
- Vollständige Dokumentation
- Dokumentation Pflegen
- Änderungen dokumentieren
- Logische Struktur dokumentieren

NET.1.1.A3 Anforderungsspezifikation für das Netz (B)
- Anforderungsspezifikation
	- Wesentliche Elemente müssen enthalten sein

NET.1.1.A4 Netztrennung in Zonen
- 3 Zonen
	- internes Netz
	- DMZ
	- Außenanbindungen
- Firewall zwischen den Zonen
	- Prinzip der Allowlist
- Zweistufige Firewall zu nicht vertrauenswürdigen Netzen
- Zustandsbehafteter Paketfilter
- P-A-P Struktur

NET.1.1.A5 Client-Server-Segmentierung (B)
- Clients und Server trennen
- Zustandsbehafteter Paketfilter zwischen Netzen
- Eigene Netzsegmente für Gastnetze

NET.1.1.A6 Endgeräte-Segmentierung im internen Netz (B)
- Nur Geräte mit ähnlichem Sicherheitsniveau pro Segment

NET.1.1.A7 Absicherung von schützenswerten Informationen (B)
- Schützenswerte Informationen müssen mit sicheren Protokollen verschlüsselt übertragen werden

NET.1.1.A8 Grundlegende Absicherung des Internetzugangs
- Internetverkehr muss über Firewall gehen

NET.1.1.A9 Grundlegende Absicherung der Kommunikation mit nicht vertrauenswürdigen Netzen
- Einstufen wie Vertrauenswürdig jedes Netz ist
- Nicht vertrauenswürdige Netze müssen wie das Internet behandelt werden

NET.1.1.A10 DMZ-Segmentierung für Zugriffe aus dem Internet
- Es muss eine DMZ ins Internet verwendet werden

NET.1.1.A11 Absicherung eingehender Kommunikation vom Internet in das interne Netz
- Zugriff aus dem Internet auf vertrauenswürdige Systeme nur über VPN

NET.1.1.A12 Absicherung ausgehender interner Kommunikation zum Internet
- Sicherheitsproxy verwenden

NET.1.1.A13 Netzplanung
- Sicherheitsrichtlinien beachten
- Regelmäßig prüfen

NET.1.1.A14 Umsetzung der Netzplanung
- fachgerecht
- Prüfung

NET.1.1.A15 Regelmäßiger Soll-Ist-Vergleich
- Regelmäßige Prüfung

### Standardanforderungen
NET.1.1.A16 Spezifikation der Netzarchitektur
- Netzwerkvirtualisierung
- Firewalls
- Clouds

NET.1.1.A17 Spezifikation des Netzdesigns
- DMZ
- Redundanzen
- Adresskonzept
- Clouds

NET.1.1.A18 P-A-P-Struktur für die Internet-Anbindung
- Firewall
- Transfernetze
- proxy-basiertes Application-Layer-Gateway

NET.1.1.A19 Separierung der Infrastrukturdienste
- Dediziertes Netzwerk

NET.1.1.A20 Zuweisung dedizierter Subnetze für IPv4/IPv6-Endgerätegruppen
- Subnetting

NET.1.1.A21 Separierung des Management-Bereichs
- dedizierten Netzsegmente

NET.1.1.A22 Spezifikation des Segmentierungskonzepts
- Segmentierung

NET.1.1.A23 Trennung von Netzsegmenten
- Schutzbedarf am höchsten vorkommenden Schutzbedarf im Netzsegment

NET.1.1.A24 Sichere logische Trennung mittels VLAN

NET.1.1.A25 Fein- und Umsetzungsplanung von Netzarchitektur und -design

NET.1.1.A26 Spezifikation von Betriebsprozessen für das Netz

NET.1.1.A27 Einbindung der Netzarchitektur in die Notfallplanung

### Anforderungen bei erhöhtem Schutzbedarf
NET.1.1.A28 Hochverfügbare Netz- und Sicherheitskomponenten
- Redundanz

NET.1.1.A29 Hochverfügbare Realisierung von Netzanbindungen
- Keine Single Points of Failure

NET.1.1.A30 Schutz vor Distributed-Denial-of-Service

NET.1.1.A31 Physische Trennung von Netzsegmenten

NET.1.1.A32 Physische Trennung von Management-Netzsegmenten

NET.1.1.A33 Mikrosegmentierung des Netzes

NET.1.1.A34 Einsatz kryptografischer Verfahren auf Netzebene

NET.1.1.A35 Einsatz von netzbasiertem DLP

NET.1.1.A36 Trennung mittels VLAN bei sehr hohem Schutzbedarf
- **keine VLANS**

---
# Zusammenfassung

- **Firewalls** zwischen den Netzwerken
	- **Allowlist** Prinzip
- **Segmentierung**
	- Geräte mit **ähnlichem Schutzbedarf** und **Anwendungszweck** in ein Netz
- **Richtlinien** erstellen
- Richtlinien **regelmäßig überprüfen**
- **DMZ** verwenden
- **Redundanzen**

---
# 6. Maßnahmen für einen Beispielbetrieb
1. **Netzaufnahme durchführen**
    - Ist-Zustand dokumentieren (Netzplan, IP-Bereiche, Übergänge)
2. **Zonenmodell einführen**
    - Büro-Netz
    - Server-Netz
    - DMZ (z. B. Webserver, Mailserver)
    - Gastnetz
3. **Netzsegmentierung umsetzen**
    - VLANs für unterschiedliche Bereiche
    - Trennung von Clients und Servern
4. **Zentrale Übergänge absichern**
    - Firewalls zwischen Zonen
5. **Dokumentation und Pflege**
    - Netzpläne aktuell halten
    - Änderungen nur nach Freigabe