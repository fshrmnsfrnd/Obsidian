---
Thema:
  - "[[BSI Grundschutz]]"
---
https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_3_Strukturanalyse/Lektion_3_node.html

**Ziel der Strukturanalyse** ist es, die hierfür erforderlichen Kenntnisse zusammenzustellen und aufzubereiten. In der Strukturanalyse vervollständigen Sie damit die Ergebnisse der zuvor durchgeführten Erstaufnahme der Prozesse, Anwendungen und IT-Systeme
#  [3.2 Objekte gruppieren](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_3_Strukturanalyse/Lektion_3_02/Lektion_3_02_node.html)
Generell gilt, dass Sie Komponenten zusammenfassen sollten, die
- vom gleichen Typ sind
- gleich oder nahezu gleich konfiguriert sind
- gleich oder nahezu gleich in das Netz eingebunden sind
- den gleichen administrativen und infrastrukturellen Rahmenbedingungen unterliegen
- die gleichen Anwendungen bedienen **und**
- den **gleichen Schutzbedarf** aufweisen.

# [3.3 Geschäftsprozesse und Informationen erheben](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_3_Strukturanalyse/Lektion_3_03/Lektion_3_03_node.html)
Ergebnisdarstellung
Für jeden Geschäftsprozess sollten Sie die folgenden Angaben vermerken
- eine eindeutige **Kennung** (Nummer oder Kürzel),
- einen **Namen** für den Prozess,
- eine kurze **Beschreibung** des Ziels, der Abläufe und der verarbeiteten Informationen,
- die für den Prozess **Verantwortlichen**
- wichtige **Anwendungen**, die für den Prozess benötigt werden.
**Beispiel**

|Kennung: Name (Art) und Beschreibung des Prozesses sowie der verwendeten Informationen|Verantwortlicher/  <br>Mitarbeiter|
|---|---|
|**GP001: Produktion** **(Kerngeschäft):**  <br>Die Produktion der Kunststoffartikel umfasst alle Phasen von der Materialbereitstellung bis hin zur Einlagerung des produzierten Materials. Hierzu gehören innerhalb der Produktion die internen Transportwege, die Produktion und Fertigung der verschiedenen Komponenten und das Verpacken der Teile.  <br>Es werden alle Informationen über Aufträge, Lagerbestände und Stücklisten verarbeitet.|Leiter Produktion/  <br>Alle Mitarbeiter|
# [3.4 Anwendungen erheben](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_3_Strukturanalyse/Lektion_3_04/Lektion_3_04_node.html)
Für jede als wesentlich identifizierte Anwendung sollten Sie **folgende** **Angaben** in einer Tabelle erfassen:
- eine eindeutige **Kennung** (Nummer oder Kürzel),
- einen **Namen** für die Anwendung,
- eine kurze **Beschreibung** des Ziels, der Funktion und der verarbeiteten Informationen,
- die für die Anwendung **Verantwortlichen**,
- die **Benutzer** dieser Anwendung.
**Beispiel**

| Bezeichnung, Name und Beschreibung der Anwendung                                                                                                                                                | Anzahl | Benutzer/  <br>Verantwortlicher   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ | --------------------------------- |
| **A001: Textverarbeitung, Präsentation, Tabellenkalkulation**  <br>Alle geschäftlichen Informationen werden in einem Office-Produkt verarbeitet: Geschäftsbriefe, Analysen oder Präsentationen. | 290    | Alle Mitarbeiter/  <br>IT-Betrieb |
**Zuordnung** der Anwendungen zu Geschäftsprozessen:

| Geschäftsprozess           | A001 | A002 | ... |
| -------------------------- | ---- | ---- | --- |
| GP001 _Produktion_         | X    |      |     |
| GP002 _Angebotswesen_      | X    | X    |     |
| GP003 _Auftragsabwicklung_ |      | X    | X   |

# [3.5 Netzplan erheben](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_3_Strukturanalyse/Lektion_3_05/Lektion_3_05_node.html)
Im Einzelnen sollte der Plan mindestens die folgenden Objekte enthalten:
- die in das Netz eingebundenen **IT-Systeme** dazu zählen Computer (Clients und Server), Netzdrucker sowie aktive Netzkomponenten (Switches, Router, WLAN-Access Points), usw.;
- die **Verbindungen zwischen diesen IT-Systemen** LAN-Verbindungen (Ethernet), Backbone-Technik (z. B. ATM), usw.
- die **Außenverbindungen der IT-Systeme** bei diesen sollte zusätzlich die Art der Verbindung gekennzeichnet sein (z. B. Internet-Anbindung, DSL), usw.

# [3.6 IT-Systeme erheben](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_3_Strukturanalyse/Lektion_3_06/Lektion_3_06_node.html)
### Zu den IT-Systemen zählen:
- alle im Netz vorhandenen **Computer** (Clients und Server), Gruppen von Computern, aktive **Netzkomponenten**, **Netzdrucker**, aber auch
- industrielle Steuerungen (Industrial Control Systems, **ICS**), dazu zählen
    - Geräte, die im Bereich Produktion und Fertigung zur Steuerung oder Überwachung eingesetzt werden, z. B. speicherprogrammierbare Steuerungen (SPS), Maschinen, die über WLAN gesteuert werden, autonome Fahrzeuge, aber auch
    - Arbeitsplatz-PCs zur Steuerung einer Maschine und die Endgeräte wie Scanner oder Drucker, die an diese PCs angeschlossen sind,
- Telekommunikationsgeräte, Mobiltelefone oder andere **mobile Geräte**
- Objekte aus dem Bereich des Internet of Things (**IoT**), also Geräte, die vernetzt sind und Daten erfassen, speichern, verarbeiten und übertragen können, z. B. Webcams, Smart-Home-Komponenten oder Sprachassistenten (auch für solche Geräte finden Sie IT-Grundschutz-Bausteine).
### Welche Angaben sind für IT-Systeme erforderlich?
Eine tabellarische Übersicht sollte für jedes IT-System die folgenden Angaben enthalten:
- eindeutige **Bezeichnung**,
- bei Gruppen: **Anzahl** der zusammengefassten IT-Systeme,
- **Beschreibung** (insbesondere sollten Sie hier den Einsatzzweck und den Typ anführen z. B. „Server für Personalverwaltung“, „Router zum Internet“),
- **Plattform** (Welcher Hardwaretyp, welches Betriebssystem?),
- **Standort** (Gebäude und Raumnummer),
- **Status** (z. B. in Betrieb, im Test, in Planung) und
- **Benutzer** und **Administrator**.

Zur Dokumentation der Beziehungen zwischen IT-Systemen und Anwendungen empfiehlt sich eine Matrix, wie sie auch zur Darstellung der Abhängigkeiten zwischen Geschäftsprozessen und Anwendungen verwendet wird.

**Beispiel**

|Bezeichung und Beschreibung|Standort|Anzahl|Benutzer/  <br>Verantwortlich|
|---|---|---|---|
|**N001 Router Internetanbindung:**  <br>Dieser Router regelt die Kommunikation zwischen dem Internet und dem internen Netz.|Serverraum BG|1|Administratoren/  <br>IT-Betrieb|
# [3.7 Räume erheben](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_3_Strukturanalyse/Lektion_3_07/Lektion_3_07_node.html)
Zur Dokumentation der Beziehungen zwischen IT-Systemen und Räumen empfiehlt sich eine Matrix, wie sie in [Lerneinheit 3.4: _Anwendungen erheben_](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_3_Strukturanalyse/Lektion_3_04/Lektion_3_04_node.html "Lerneinheit 3.4: Anwendungen erheben") auch verwendet wird.
**Beispiel**

| Bezeichnung und Beschreibung  | Art        | Lokation       |
| ----------------------------- | ---------- | -------------- |
| GB1 Produktionsgebäude        | Gebäude    | Bonn-Beuel     |
| R001 Serverraum Bad Godesberg | Serverraum | GB1, Raum 1.02 |
