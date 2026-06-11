---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
>Android ist ein **Open-Source-, Linux-basierter Software-Stack**, der für eine Vielzahl von Geräten und Formfaktoren entwickelt wurde. 

![[Pasted image 20251127134405.png]]

# Linux Kernel
---
Die **Grundlage** der Android-Plattform ist der Linux-Kernel. Beispielsweise stützt sich die Android Runtime (ART) auf den Linux-Kernel für zugrundeliegende Funktionen wie Threading und Low-Level-Speicherverwaltung. Der Linux-Kernel ermöglicht es Android, wichtige Sicherheitsfunktionen zu nutzen und erlaubt Geräteherstellern die Entwicklung von Hardwaretreibern für einen bekannten Kernel.

# Hardwareabstraktionlayer (HAL)
---
Die Hardwareabstraktionsschicht (HAL) stellt **Standardschnittstellen** bereit, die Geräte-Hardware-Funktionen für das übergeordnete Java-API-Framework verfügbar machen. Sie besteht aus mehreren Bibliotheksmodulen, von denen jedes eine Schnittstelle für eine bestimmte Art von Hardwarekomponente implementiert, z. B. die **Kamera oder das Bluetooth-Modul**. Wird aus dem Framework die Hardware über einen API-Call angesprochen, wird das Modul der zugehörigen Hardwarekomponente geladen.

# Android Runtime (ART)
---
Ab Android Version 5.0 (API-Level 21) oder höher läuft jede App in einem **eigenen Prozess** und mit einer eigenen Instanz der ART. ART wurde programmiert, um **mehrere virtuelle Maschinen** auf Geräten mit wenig Arbeitsspeicher auszuführen, indem **DEX-Dateien** ausgeführt werden. DEX ist ein Bytecode-Format, das speziell für Android entwickelt wurde und für **minimalen Speicherbedarf** optimiert ist. Der Compiler d8 kompiliert während des Build-Prozesses JAVA-Bytecode in DEX-Bytecode. 

Wichtige Features der ART:
- Ahead-of-time (AOT) and Just-in-time (JIT) Kompilierung 
- optimierter Garbage Collector 
- Ab Android 9 (API Level 28) wird DEX-Bytecode in kompakten Maschinencode übersetzt. 
- bessere Debugging-Unterstützung

Vor Android Version 5.0 (API Level 21) war Dalvik die Android Runtime. Wenn Ihre App auf ART gut läuft, sollte sie auch auf Dalvik funktionieren, aber das Gegenteil ist möglicherweise nicht der Fall.

# Java API Framework
---
Der gesamte Funktionsumfang des Android-Betriebssystems steht über APIs zur Verfügung, die in Java geschrieben sind. Diese APIs bilden die Bausteine, die zum Erstellen von Android-Apps benötigt werden. 

Das Framework enthält folgende Komponenten: 
- Umfangreiche und erweiterbare **View-Komponenten**, mit denen Sie die Benutzeroberfläche einer App erstellen können, einschließlich **Listen, Grids, Textfelder, Schaltflächen** und sogar einen integrierbaren Webbrowser. 
- Einen **Ressourcen-Manager**, der Zugriff auf **Nicht-Code-Ressourcen** wie lokalisierte Zeichenfolgen, Grafiken und Layout-Dateien bietet. 
- Einen **Notification Manager**, mit dem alle Apps benutzerdefinierte Warnungen in der Statusleiste anzeigen können. 
- Einen **Aktivitäts-Manager**, der den Lebenszyklus von Apps verwaltet und einen gemeinsamen Navigations-Back-Stack bereitstellt. 
- **Content Provider**, die es Apps ermöglichen, auf **Daten aus anderen Apps**, z. B. der Kontakte-App, zuzugreifen oder ihre eigenen Daten zu teilen. 
- Entwickler haben vollen Zugriff auf dieselben Framework-APIs, die Android-System-Apps verwenden.

# System Apps
---
Android kommt mit einer Reihe von System-Apps für **E-Mail, SMS-Messaging, Kalender, Internet-Browsing, Kontakte und mehr**. Apps, die in der Plattform enthalten sind, haben keinen besonderen Status unter den Apps, die der Benutzer installieren möchte. So können Standard Apps geändert werden (Ausnahmen: z. B. die Einstellungs-App). Die System-Apps fungieren sowohl als **Apps für Benutzer** als auch als **Bereitstellung wichtiger Funktionen**, auf die Entwickler von ihrer eigenen App aus zugreifen können. 

# Android Bibliotheken im Detail
---
>Dabei handelt es sich um eine Reihe von java-basierten Bibliotheken, die für die Android-Entwicklung spezifisch sind.

| Bibliothek       | Beschreibung                                                                                                                                                                                                      |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| android.app      | Bietet Zugriff auf das Anwendungsmodell und ist der Eckpfeiler aller Android-Anwendungen.                                                                                                                         |
| android.content  | Erleichtert den Zugriff auf Inhalte und das Messaging zwischen Anwendungen.                                                                                                                                       |
| android.database | Wird für den Zugriff auf Daten verwendet, die von Content Providers veröffentlicht wurden, und enthält SQLite-Datenbankverwaltungsklassen.                                                                        |
| android.graphics | Eine Low-Level-API für 2D-Grafikzeichnungen mit Farben, Punkten, Filtern, Rechtecken und Leinwänden.                                                                                                              |
| android.hardware | Präsentiert eine API, die Zugriff auf Hardware wie den Beschleunigungsmesser und den Lichtsensor bietet.                                                                                                          |
| android.opengl   | Eine Java-Schnittstelle zur OpenGL ES 3D-Grafik-Rendering-API.                                                                                                                                                    |
| android.os       | Bietet Anwendungen Zugriff auf Standardbetriebssystemdienste, einschließlich Nachrichten, Systemdienste und prozessübergreifende Kommunikation.                                                                   |
| android.media    | Bietet Kurse zur Wiedergabe von Audio und Video. android.net: Eine Reihe von APIs, die den Zugriff auf den Netzwerk-Stack bieten. Enthält android.net.wifi, das Zugriff auf den wireless-Stack des Geräts bietet. |
| android.print    | Enthält eine Reihe von Klassen, mit denen Inhalte aus Android-Anwendungen an konfigurierte Drucker gesendet werden können.                                                                                        |
| android.provider | Eine Reihe von Komfortklassen, die zugriff auf Standarddatenbanken von AndroidInhaltsanbietern bieten, z. B. auf Datenbanken, die von den Kalender- und Kontaktanwendungen verwaltet werden.                      |
| android.text     | Wird verwendet, um Text auf einem Gerätedisplay zu rendern und zu bearbeiten.                                                                                                                                     |
| android.util     | Eine Reihe von Dienstprogrammklassen zum Ausführen von Aufgaben wie Zeichenfolgenund Zahlenkonvertierung, XML-Handling sowie Datums- und Uhrzeitmanipulation.                                                     |
| android.view     | Die grundlegenden Bausteine von Anwendungsbenutzeroberflächen.                                                                                                                                                    |
| android.widget   | Eine umfangreiche Sammlung vorgefertigter Benutzeroberflächenkomponenten wie Schaltflächen, Beschriftungen, Listenansichten, Layout-Manager, Optionsfelder usw.                                                   |
| android.webkit   | Eine Reihe von [[Klassen in Java\|Klassen]], mit denen Web-Browsing-Funktionen in Anwendungen integriert werden können.                                                                                           |
# Application Frameworks im Detail
>Das Application Framework bietet eine Reihe von Diensten, die zusammen die Umgebung bilden, in der Android-Anwendungen ausgeführt und verwaltet werden.

| Framework             | Beschreibung                                                                                                                           |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Activity Manager      | Steuert alle Aspekte des Anwendungslebenszyklus und des Aktivitätsstapels.                                                             |
| Content Providers     | Ermöglicht es Anwendungen, Daten zu veröffentlichen und mit anderen Anwendungen zu teilen.                                             |
| Ressource Manager     | Bietet Zugriff auf eingebettete Ressourcen ohne Code wie Zeichenfolgen, Farbeinstellungen und Layouts der Benutzeroberfläche.          |
| Notifications Manager | Ermöglicht es Anwendungen, Warnungen und Benachrichtigungen für den Benutzer anzuzeigen.                                               |
| View System           | Ein erweiterbarer Satz von [[Views\|Views]], die zum Erstellen von Benutzeroberflächen verwendet werden.                    |
| Package Manager       | Das System, mit dem Anwendungen Informationen über andere Anwendungen herausfinden können, die derzeit auf dem Gerät installiert sind. |
| Telephony Manager     | Stellt der Anwendung Informationen über verfügbare Telefondienste bereit: z. B. Status und Teilnehmerinformationen.                    |
| Location Manager      | Bietet Zugriff auf die Ortungsdienste, sodass eine Anwendung Updates zu Standortänderungen erhalten kann.                              |