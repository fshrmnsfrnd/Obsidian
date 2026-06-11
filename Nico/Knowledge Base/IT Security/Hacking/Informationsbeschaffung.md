---
Fach: "[[ITS]]"
---
# Begriffe
- **Reconnaissance** (Erkundung)
	- umfasst aktive und passive Methoden der Informationsbeschaffung.
- **Footprinting** 
	- Informationsbeschaffung über öffentlich zugängliche Quellen. Man steht nicht im direkten Kontakt mit dem Ziel. Dies wird auch als OSINT (Open Source Intelligence) bezeichnet. (passive Methode)
- **Scanning** 
	- Aktives Erkunden durch Port- und Vulnerability Scanning, Banner-Grabbing etc. im Zielnetzwerk (aktive Methode)
- **Enumeration** (Aufzählung)
	- Hier werden bestimmte Dienste systematisch abgefragt (DNS, SNMP, NETBOIS)
# Footprinting
>Informationsbeschaffung über öffentlich zugängliche Quellen. Man steht nicht im direkten Kontakt mit dem Ziel. Dies wird auch als OSINT (Open Source Intelligence) bezeichnet. (passive Methode)
### Suchmaschinen 
Über Suchmaschinen kann man sehr viel über das Ziel herausfinden. z.B: 
- **Normale Suchmaschine** für aktuelle Infos Google-Hacking
	- Google bietet eine große Anzahl an Suchoperatoren, die die Suche zielgerichteter machen. Eine Sammlung der Möglichkeiten findet man hier: https://www.exploit-db.com/google-hacking-database Kurzanleitungen zum google-Hacking: https://www.uni-erfurt.de/fileadmin/einrichtung/bibliothek/Themen/Lernangebote/Google_Hacks.pdf
- **WayBack Machine** 
	- Ein Internetarchiv https://archive.org/ 
- **Shodan**
	- Hiermit können Sie Geräte finden, die mit dem Internet verbunden sind (Registrierung notwendig) https://www.shodan.io/ 
- **Personensuchmaschinen** 
	- z.B. https://webmii.com/ https://www.identcheck.net/ (Kostenpflichtig)
- **Social Media Footprinting** 
	- Auf Social Media werden viele persönliche Informationen geteilt, die bei einem Hacking-Angriff genutzt werden können. Geduld ist gefragt.
### DNS
- **Whois**-Abfrage 
	- Beim Registrieren einer Domain werden persönliche und technische Daten des Besitzers gespeichert. Eine Whois-Abfrage gibt einige der Informationen aus. Es kann nach IP-Adressen oder Domains gesucht werden. Durch die strengen Datenschutzgesetze in Europa sind die Ergebnisse nicht mehr sehr aussagekräftig. Beispiel: https://webwhois.denic.de/ 
- Tools zur DNS-Namensauflösung 
	- Windows: nslookup Linux: dig, nslookup und host 
### Email 
Im Header einer Email können Sie Informationen zu den verwendeten Servern finden. 
### Website Footprinting
- Metagoofil (Kali): Dateien auf einer Website durchsuchen https://www.kali.org/tools/metagoofil/ 
- Web-Site-Copier : eine ganze Website herunter laden und in Ruhe durchsuchen. 
	- Tools z.B: https://www.httrack.com/ http://www.webextractor.com/ (Kostenpflichtig mit Filterfunktion)
# Reconnaissance Frameworks
- recon-ng 
	- Kommandozeilenbasiertes freies Framework, das verschiedene Aspekte der Informationsbeschaffung vereint. recon-ng steht in Kali zur Verfügung. https://github.com/lanmaster53/recon-ng/wiki 
- Anleitungen 
	- https://hackertarget.com/recon-ng-tutorial/ 
	- https://youtu.be/1RCqOhb0yxE?si=CKlqWx_P-ekdweE2 
- Maltego
	- Maltego ist ein grafisches Tool zur Informationsbeschaffung. Es ist nur sehr eingeschränkt frei nutzbar und muss in Kali installiert werden. https://www.maltego.com/ 
- Onlinekurs 
	- https://spark.maltego.com/course/maltego-foundations-1

