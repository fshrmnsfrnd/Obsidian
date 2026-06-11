---
Fach:
Thema:
  - "[[Networks]]"
---
# Verkabelung
---
Seit dem **10BaseT-Standard** werden für Netzwerke keine **Koaxialkabel** sonder **Twisted-Pair-Kabel** (verdrillte Kupferkabel) verwendet. Bei einer Twisted-Pair-Verkabelung wird eine sternförmige Topologie verwendet, bei welcher jede Station eine Punkt-zu-Punkt-Verbindung zu einem Zentralen Knoten hat (damals noch Hubs).  
Diese Twisted-Pair Kabel werden in verschiedene Kategorien (**CAT 1-8**) unterteilt. Je höher die Nummer desto Leistungsfähiger sind die Kabel.  
Bei TP-Kabeln sind vier Adern Paare, welche mit sich selbst verdrillt sind, miteinander verdrillt.  
Durch diesen Aufbau sind die Kabel relativ resistent gegen übersprechen:
![[Pasted image 20251122235945.png]]
Auf jedem Adern Paar wir ein **Komplementärsignal** gesendet, was bedeutet auf einer Ader sind die Signale von `0` bis `+2,8V` und auf der anderen von `0` bis `−2,8V`. Dadurch kann zu einem eine eingestreute Störung ([[Crosstalk]]) weitestgehend ausgefiltert werden und zum anderen reduziert es deutlich die Abstrahlung von elektromagnetischen Wellen. Also erhöht sich die **EMV** (Elektromagnetische Verträglichkeit.)

# Liste der Standards
---
Seit 10Base-T wird mit einer **Segmentlänge** von $100m$ gerechnet, dabei sind $5m$ **Patchkabel** bereits eingerechnet somit bleiben noch `95m` für die feste Verkabelung (**Permanent Link**) übrig.  

| **Standard** | **Adernpaare** | **Übertragungsrate**   | **min. CAT**              | **Duplex**                            | **Verbindungstechnik** |
| ------------ | -------------- | ---------------------- | ------------------------- | ------------------------------------- | ---------------------- |
| 100Base-T    | 4              | $100 \frac{MBit}{s}$   | 5                         | Halbduplex mit CSMA/CD und Vollduplex | RJ45                   |
| 1000Base-T   | 4              | $1000 \frac{MBit}{s}$​ | 5 (5e ist aber Empfohlen) | Vollduplex                            | RJ45                   |
# Standards
---
## 1000Base-T
### Übertragungsrate optimieren
Damit 1000Base-T auf den zur damaligen Zeit standardmäßig verlegten CAT-5 Kabeln funktionieren konnte, musste die eigentliche **Übertragungsrate** über das Kabel drastisch Reduziert werden. Das hat man wie folgt gemacht:  
- Um die Bitrate von **1250 MBit/s** auf **1000 MBit/s** zu reduzieren wurde auf die **8B/10B-Kodierung** verzichtet 
-  Es werden jetzt alle **4 Adernpaare** des TP-Kabels verwendet, dadurch reduziert sich die Datenübertragungsrate pro Adernpaar auf ein Viertel, also 250 MBit/s  
- Jetzt werden zum Senden und Empfangen **nicht** mehr eigene Kanäle verwendet (Es wird auf allen Adernpaaren gleichzeitig gesendet und empfangen). Damit das funktioniert wird beim Empfangen das gesendete Signal abgezogen, wodurch nur noch die zu empfangenden Daten übrig bleiben (**Echo-Cancellation-Verfahren**). Damit dies Funktioniert müssen Sender und Empfänger auf dem selben Takt arbeiten, weshalb einer eine **Master** und der andere eine **Slave-rolle** erhält 
- Von den 3-wertigen Übertragungscode wird jetzt ein **5-Wertiges 4D-PAM5-Verfahren** verwendet. (4 Adern Paare mit Pulsamplitudenmodulation mit 5 Stufen) 
### Signalprozessor
Da bei 1000Base-T auf allen Adern Paaren Daten übertragen werden entsteht untereinander mehr [[Crosstalk]]. Um diese Störung herauszurechnen besitzt jedes Adernpaar für jedes benachbarte (hier 3) einen **NEXT/FEXT-Cancellationer**, also 1000Base-T insgesamt 12  

### Startup-Protokoll
Nachdem eine 1000Base-T-Komponente zurückgesetzt wurde wird ein Startup-Protokoll nach dem Empfangen des **Fast-Link-Pulses** gestartet. Dieses hat 5 Aufgaben:  
    - Automatische **MDI/MDI-X-Einstellung** (Kein Crossover-Kabel mehr nötig)  
    - Festlegung der **Übertragungsrate**  
    - Festlegung der **Master-Slave-Rolle**  
    - Einstellung der **DSP-Filter** (Einstellen der NEXT/FEXT und Echo-Cancellationer)