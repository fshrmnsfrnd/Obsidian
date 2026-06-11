---
Fach: "[[AWM]]"
---
# Erwartungen der Nutzer
---
- Intuitives Design
- Leicht zu bedienen
- Gute Performance
- Datenschutz
- Laufend weiterentwickeln

# Entwicklungsprozess
---
## 1. Analyse
- Projektumfang festlegen
	- Zielgruppe
	- Projektziel
	- Use-Cases
	- Beziehungen beteiligter Systeme
	- Schnittstellen zu anderen Systemen
## 2. UX Design
- Erstellung von Wireframes (Schematische Darstellung der Benutzerführung)
- Erstellung eines klickbaren Prototypen
## 3. UI Design
- Optimale Gestaltung und Interaktion
- Ziel: Leicht zu bedienen und intuitiv Nutzen
## 4. Softwareentwicklung
Da die Produktzyklen in der App-Entwicklung sehr kurz sind, werden oft agile Vorgehensmodelle (z.B. [[SCRUM]]) verwendet. Als erste Version wird ein Minimum Viable Product (MVP) entwickelt. Das ist ein Produkt, das einen brauchbaren Funktionsumfang bietet und auf dem Mark existenzfähig ist. Diese Vorgehen ermöglicht sehr schnell, aus dem Nutzerfeedback zu lernen. In weiteren Iterationen wird dann das Produkt weiterentwickelt. Das Risiko von Fehlentwicklungen wird so minimiert. Die Ergebnisse jeder Iteration werden getestet.

# Wichtige Aspekte
---
- Energieverbrauch optimieren
- Viele Sensoren können verwendet werden (Kompass, Neigung, usw.)
- Programmiersprachen und Frameworks
	- Android
		- Kotlin
		- Java (deprecated)
	- iOS
		- Swift
		- Objective-C (deprecated)
	- Platformübergreifend
		- Flutter
		- [[React]] Native
		- Xamarin
- Eine App kann sich nicht auf zuverlässige Datenverbindung verlassen
- Datensicherheit
- Apps kommen über einen App Store
- Unterschiedliche Bildschirmgrößen müssen berücksichtigt werden

# Native Apps
---
>Eine **native App** ist eine Anwendung, die speziell **für ein bestimmtes Betriebssystem** entwickelt wurde – also **iOS**, **Android** oder eine andere Plattform.

- **Plattformspezifisch**
    - iOS-Apps werden z. B. in **Swift** oder **Objective-C** programmiert.
    - Android-Apps in **Kotlin** oder **Java**.
- **Volle Hardware- und Systemzugriffe**
    - Native Apps können **Kamera, GPS, Mikrofon, Sensoren, Benachrichtigungen** direkt nutzen.
    - Performance ist hoch, weil sie direkt auf die APIs des Betriebssystems zugreifen.
- **Hohe Performance & Stabilität**
    - Schneller als plattformübergreifende Apps (wie Flutter oder [[React]] Native).
    - Besonders wichtig für Spiele, Multimedia oder rechenintensive Apps.
- **Verteilung über App-Stores**
    - iOS → Apple App Store
    - Android → Google Play Store (oder alternative Stores)
# Web App
---
>Eine **Web-App** ist eine Anwendung, die **über einen Webbrowser** läuft, anstatt direkt als native App auf einem Gerät installiert zu werden. Sie wird mit **Web-Technologien** wie **HTML, CSS und [[JavaScript]]** entwickelt.

- **Plattformunabhängig**
    - Läuft auf **allen Geräten**, die einen modernen Browser haben (PC, Tablet, Smartphone).
    - Kein App-Store nötig.
- **Installation optional**
    - Kann als **Progressive Web App (PWA)** „installiert“ werden, sodass sie wie eine normale App aussieht und sich verhält.
- **Updates sofort verfügbar**
    - Änderungen am Server werden direkt für alle Nutzer wirksam.
- **Eingeschränkter Hardwarezugriff**
    - Browser erlauben Zugriff auf Kamera, GPS, Mikrofon etc., aber oft **nicht so tief** wie native Apps.
# Hybrid App
---
>Eine **Hybrid-App** ist eine Art Mischung aus **nativer App** und **Web-App**. Sie kombiniert Elemente beider Ansätze, um **plattformübergreifend** zu funktionieren, aber trotzdem als installierbare App auf Smartphones verfügbar zu sein.

1. Plattformübergreifend
    - Ein Großteil des Codes ist **für mehrere Betriebssysteme nutzbar** (Android, iOS).
    - Meist mit **Web-Technologien** (HTML, CSS, [[JavaScript]]) geschrieben.
2. Native „Hülle“
    - Läuft innerhalb einer **nativen App-Shell** oder eines Containers (z. B. Cordova, Capacitor).
    - Dadurch kann sie auf **Gerätefunktionen** wie Kamera, GPS oder Push-Benachrichtigungen zugreifen.
3. Verteilung über App-Stores
    - Wie native Apps, müssen sie über **Google Play Store** oder **Apple App Store** veröffentlicht werden.

| Vorteile                                                                        | Nachteile                                                                               |
| ------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Eine **Codebasis für mehrere Plattformen** → spart Entwicklungszeit und Kosten. | Performance kann schlechter sein als bei **echten nativen Apps**.                       |
| Zugriff auf viele native Funktionen durch Plugins.                              | Komplexere Plugins nötig, um auf bestimmte Gerätefunktionen zuzugreifen.                |
| Updates teilweise zentral steuerbar über Web-Technologien.                      | Nicht immer so flüssig wie native Apps, besonders bei grafisch aufwendigen Anwendungen. |
# In-App Käufe
---
>**In-App-Käufe** (englisch: _In-App Purchases_, kurz IAP) sind **optionale Käufe innerhalb einer App**, die Nutzer zusätzlich zum Download oder zur Nutzung tätigen können.

## Merkmale:
- Innerhalb der App verfügbar
    - Nutzer müssen die App nicht verlassen, um etwas zu kaufen.
    - Beispiele: Spielwährung, Premium-Funktionen, Abos, virtuelle Güter.
- Verschiedene Arten
    - **Einmalige Käufe:** z. B. neues Level, spezielles Werkzeug oder Bonusfunktion.
    - **Abonnements:** z. B. Premium-Mitgliedschaft, erweiterter Cloud-Speicher.
    - **Virtuelle Währung / Items:** z. B. Münzen, Edelsteine oder kosmetische Gegenstände in Spielen.
- Zahlungsabwicklung über App-Store
    - Bei iOS über **Apple App Store**, bei Android über **Google Play Store**.
    - Stores behalten meist einen Prozentsatz (z. B. 15–30 %) als Provision ein.