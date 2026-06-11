---
Fach: "[[Berufsschule]]"
Thema:
  - "[[Networks]]"
---
**WLAN** _(oder in den USA auch Wi-Fi genannt)_ steht für **W**ireless **L**ocal **A**rea **N**etwork. Es ist ein lokales Netzwerk bei dem die Teilnehmer über Funk Kommunizieren. Im OSI-Modell würde WLAN auf der Schickt 2 liegen, da hier mittels MAC-Adressen gearbeitet werden.
# Betriebsarten
---
## Infrastruktur
Im Modus Infrastruktur wird eine zentrale Netzwerk-Komponente (**AP** oder auch _**A**cess-**P**oint_) benötigt. Ein WLAN hat immer einen eindeutigen Namen, den **SSID** (**S**ervifce **S**et **Id**entifier). Dieser ist immer Case-Sensitive und kann über den SSID-Broadcast bekannt gemacht werden.  
![[Pasted image 20260105173709.png]]
### Mesh
Bei einem Mesh-WLAN teilen sich mehrere APs das selbe WLAN mit der selben SSID. die Einstellungen werden dann von einem WLAN-Controller zentral verwaltet. Dadurch kann die Reichweite und die Geschwindigkeit optimiert werden. Die Verwaltung wird ebenfalls vereinfacht.  
Oft sind Meshs herstellerspezifisch, dass heißt die APs und der WLAN-Controller müssen vom selben Hersteller sein.
## Ad-Hoc
Im Ad-Hoc-Modus gibt es keine zentrale Netzwerk-Komponente. Die Geräte kommunizieren untereinender.  
![[Pasted image 20260105173722.png]]
# Standards
---
Die WLAN-Standards werden von der IEEE festgelegt.
![[YvJQMJmKBh-700.webp]]

# Optimierung von WLAN
---
- breitere Kanäle (20/40/80/160 MHz) bzw. mehrere Frequenzbereiche gleichzeitig nutzen (2,4/5 GHz)
- leistungsfähigere Verfahren (=> bessere Standards) verwenden
    - 802.11n: QAM64
    - 802.11ac: QAM256
    - 802.11ax: QAM1024
- mehrere Datenströme für Up-und Download verwenden (**MIMO** oder auch **m**ultiple **i**nput **m**ultiple **o**utput)
- mehrere Datenströme für Up-und Download mit dynamischer Anzahl pro Gerät (**Multi-User-MIMO**)
- Richtwirkung der Antenne dynamisch Anpassen
- Lastverteilung, wählen für Dual-Band fähige Clients den günstigsten Frequenzbereich wählen (**Band-Steering**)
## Beispiel an unterschiedlichen Standards
![[I4vCI-OVd2-700.webp]]

# Vor- und Nachteile
---

|**Nachteile**|**Vorteile**|
|---|---|
|schnelle Auslastung bei Vielen Teilnehmern|Große Mobilität|
|Störung durch andere Elektrische Geräte (z. B. Mikrowelle)|keine starke Bindung an Infrastruktur|
|unstabil (Verbindungsabbrüche, Leistungsschwankungen, Reichweitenreduktion, Ausleuchtung)|günstiger als viele Kabel zu verlegen|
|schwierig zu verwalten||
|Viele Fehlermöglichkeiten bei Konfiguration (z. B. Falsche Frequenz Wahl)||
|Leichtere Lauschangriffe (**Brute Force Attacken**)||
|nicht autorisierte APs (**Rogue AP**)||
|abfangen, löschen oder einschleusen von Daten||
|||
# Sicherheitsmaßnahmen
---
- Standard-Passwörter ändern
- WPS deaktivieren
- APs nur per LAN konfigurieren
- Verschlüsselung aktivieren (min. WPA2)
    - WEP veraltet und **UNSICHER**
    - WPA veraltet und **NUR TEILS SICHER**
    - WPA2 aktueller Standard **sicher** kann aber geknackt werden
    - WPA3 neuster Standard aktuell noch **sehr sicher** (2022)
- SSID ohne Rückschlussmöglichkeit auf Hardware wählen
- Nur verwendete Geräte einschalten
- Firewalls einsetzen
- Regelmäßig Firmware aktualisieren