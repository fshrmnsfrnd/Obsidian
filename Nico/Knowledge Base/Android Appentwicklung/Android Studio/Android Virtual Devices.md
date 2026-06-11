---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
  - "[[Operating System]]"
---
AVDs sind im Wesentlichen *Emulatoren*, mit denen Android-Anwendungen getestet werden können, ohne dass die Anwendung auf einem physischen Android-basierten Gerät installiert werden muss. Ein AVD kann so konfiguriert werden, dass es eine Vielzahl von **Hardwarefunktionen emuliert**, einschließlich Optionen wie Bildschirmgröße, Speicherkapazität und das Vorhandensein oder nicht Vorhandensein von Funktionen wie einer Kamera, GPS-Navigationsunterstützung oder eines Beschleunigungsmessers. Im Rahmen der Standardinstallation von Android Studio werden eine Reihe von Emulator-Vorlagen installiert, mit denen AVDs für eine Reihe verschiedener Geräte konfiguriert werden können. Benutzerdefinierte Konfigurationen können erstellt werden, um jedem physischen Android-Gerät zu entsprechen, indem Eigenschaften wie Prozessortyp, Speicherkapazität, sowie Größe und Pixeldichte des Bildschirms angegeben werden. 

# Erstellen eines neuen AVDs
![[Pasted image 20251127152422.png]]

1. Wählen Sie als Form Factor die Option Phone aus. 
2. Wählen Sie die Pixel 4-Geräteoption und klicken Sie auf Weiter. 
3. Wählen Sie auf dem Bildschirm Gerätekonfiguration die gewünschte Android x86-API und die Services aus. Auf der Registerkarte zusätzliche Einstellungen können weitere Einstellungen vorgenommen werden. 
4. Klicken Sie auf Finish, um das AVD zu erstellen 
5. Nachdem das AVD erstellt wurde, kann der AVD-Manager geschlossen werden. Für zukünftige Änderungen am AVD, öffnen Sie einfach den AVD-Manager erneut.

![[Pasted image 20251127152538.png]]

# Starten des Emulators
![[Pasted image 20251127152625.png]]

# Ausführen der Anwendung im AVD
---
Um die Anwendung zu starten, klicken Sie entweder auf das grüne Dreieck, oder wählen Sie die Menü-Option `Run > Run ‘App‘` oder verwenden Sie die `Strg-R`.

Wenn während des Startvorgangs Probleme auftreten, enthält das Run-Fenster Informationen, um die Ursache des Problems festzustellen.

# Ausführen auf mehreren Geräten
---
![[Pasted image 20251127153912.png]]
