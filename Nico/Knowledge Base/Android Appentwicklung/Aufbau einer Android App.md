---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
>Eine Android Applikation ist zu großen Teil in **Java oder Kotlin** geschrieben. Sie wird zur Laufzeit in einer eigenen **DVM** ausgeführt.  Wird die Applikation zur Verwendung auf einem Endgerät oder dem Emulator gebaut, wird aus dem Java Code ein in der DVM ausführbarer Bytecode. Dieser Bytecode wird in einer Dex-Datei (Dalvik Executable) gespeichert; er ist ein zentrales Dateiformat im Android-Ökosystem. Dieser Bytecode unterscheidet sich an mehreren Stellen von einem herkömmlichen Java Byte Code.

# Inhalt des `apk` Pakets
---
Alle Bestandteile einer Applikation in Android in einer Art Zip- bzw. JAR-Datei gepackt. Dieses Paket bekommt die Dateiendung  `.apk` und wird vom Play Store auf das Endgerät kopiert und dort installiert. 

Das Paket enthält typischerweise die folgenden Verzeichnisse und Dateien:
- Verzeichnis ``META-INF/``:
	- `MANIFEST.MF`: Das Manifest in kompilierter Form 
	- `CERT.RSA`: das Zertifikat, mit dem die Applikation signiert wurde 
	- `CERT.SF`: eine Liste aller Ressourcen und das SHA-1-Digest 
- Verzeichnis ``res/``: Bibliotheken, die nicht in resources.arc kompiliert wurden. 
- Verzeichnis `lib/`: Der prozessor-spezifische, kompilierte Code (auch native Bibliotheken) 
	- `armeabi`: kompilierter ARM-Code 
	- `armeabi-7`: kompilierter ARMv7-Code 
	- `x86`: kompilierter x86-Code 
	- `mips`: kompilierter MIPS-Code 
- Verzeichnis `assets/` : Beliebige Zusatzdateien, die die App nutzt (z. B. Fonts, Datenbanken, JSON Dateien). Diese Inhalte werden nicht wie `res/` vorkompiliert, sondern bleiben im Originalzustand. 
- `resources.arsc`: Kompilierte Ressourcentabelle mit IDs, die in der App auf Ressourcen (z. B. Texte, Farben, Layouts) verweisen. 
- `AndroidManifest.xml`: Ein weiteres Manifest mit wichtigen Metainformationen für die Applikation in codierter Form.  
- `classes.dex`: Der kompilierte Dalvik- / ART-Bytecode der Anwendung.

# Bestandteile der Android Applikation
---
Android-Manifest 
Jede Android-Applikation besitzt eine besondere Datei, die allgemeine Informationen über die Applikation beinhaltet, wie z.B. den Namen, die SDK-Version, die eigene Versionsnummer, angeforderte Berechtigungen sowie Hard- und Softwareanforderungen. Diese Datei heißt AndroidManifest.xml oder kurz AndroidManifest. Die codierten Informationen innerhalb dieser Datei werden während der Installation vom System ausgewertet, um so dem Nutzer die Berechtigungen anzuzeigen, die er akzeptieren muss, bevor die Applikation erfolgreich installiert werden kann. Des Weiteren sind in ihr auch sämtliche Activities enthalten, die als Einstiegspunkte in die Applikation dienen können. Zusätzlich kann man im Android-Manifest erkennen, ob die Applikation auf externe Events wartet, um besondere Aktionen auszuführen (z.B. sobald eine SMS mit einem speziellen Text auf dem Gerät eintrifft, startet die Applikation und zeigt dem Nutzer eine Pop-up-Nachricht an). 

## Activities 
- Visuelle und Logische Einheit einer App
- Stellt UI zur Verfügung die Eingaben ermöglicht

## Services 
- Laufen im Hintergrund ohne Nutzerinterface
- Sind im Manifest deklariert
- Müssen dem Service Manager bekannt sein

## Broadcast Receiver 
- Listener für System- und App-Events

## Shared Preferences 
- Speichern kleine Datenmengen einer App als Key-Value-Store 

## Intents 
Ein Intent ist das Kommunikationsmittel in Android, mit dem man entweder innerhalb einer Anwendung Komponenten wechselt oder zwischen Apps Funktionen und Daten austauscht. 

Es gibt zwei Varianten von Intents: 
**explizite Intents:** 
	Diese geben eine konkrete Ziel-Komponente an
**implizite Intents:** 
	Diese beschreiben nur eine Aktion, die ausgeführt werden soll
## Content Provider 
 - Einziger Weg Daten zwischen Apps auszutauschen
 - Es gibt im System keinen gemeinsam genutzten Speicherbereich