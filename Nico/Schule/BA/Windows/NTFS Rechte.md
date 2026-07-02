---
Thema:
  - "[[Microsoft]]"
  - "[[Windows Client]]"
  - "[[Schule/BA/Windows Server/Windows Server|Windows Server]]"
---
# Dateizugriffsrechte unter Windows
---
Es gibt zwei Arten von Rechten: - Lokaler Zugriff: Dateisystemrechte (häufig NTFS). - Netzwerkzugriff: zusätzlich Freigaberechte. - Zugriff über das Netz erfordert sowohl Freigabe- als auch NTFS‑Rechte. - Fokus hier: NTFS‑Rechte.
# NTFS‑Rechte
---

| Recht | Bedeutung für Dateien | Bedeutung für Verzeichnisse |
|---|---|---|
| Lesen (Read) | Datei lesen; Attribute, Besitzer und Rechte anzeigen | Dateien und Unterverzeichnisse anzeigen; Rechte und Attribute anzeigen |
| Schreiben (Write) | Datei überschreiben; Attribute ändern; Besitzer und Rechte anzeigen | Ordnerinhalt anzeigen (list) |
| Ordnerinhalt anzeigen (List) | — | Dateien und Unterverzeichnisse des Verzeichnisses anzeigen |
| Lesen & Ausführen (Read, Execute) | Programme ausführen; Leseberechtigung | Lesen und in Unterverzeichnisse wechseln |
| Ändern (Modify) | Dateien verändern und löschen; beinhaltet Lesen, Ausführen, Schreiben | Verzeichnis löschen; beinhaltet Lesen, Ausführen, Schreiben |
| Vollzugriff (Full Control) | Rechte ändern, Besitz übernehmen, Unterordner und Dateien löschen; alle anderen Rechte | Rechte ändern, Besitz übernehmen, Unterordner und Dateien löschen; alle anderen Rechte |
- Dateien/Verzeichnisse erben Rechte vom übergeordneten Verzeichnis (sofern nicht in Erweitert anders eingestellt). - Das List‑Recht kann nicht an Dateien vererbt werden. - Vollzugriff nur sparsam vergeben (für Tauschordner meist nicht nötig).
# NTFS‑Rechte konfigurieren
---
- Rechtsklick → Eigenschaften → Register Sicherheit zum Anzeigen und Bearbeiten von Rechten. - Klick auf Bearbeiten: Rechte ändern; Benutzer/Gruppen hinzufügen oder entfernen. - „Authentifizierte Benutzer“ = alle lokalen Konten; „SYSTEM“ = Betriebssystem und wichtige Dienste (Eintrag möglichst nicht verändern). - Button Erweitert → Zugriff auf erweiterte NTFS‑Einstellungen:  - Register Berechtigungen für feinere Rechtevergabe und Steuerung der Vererbung.  - Vererbung deaktivieren: bisher geerbte Rechte in normale Rechte konvertieren (empfehlenswert) oder entfernen.  - Besitzer ändern oberhalb der Register.  - Register Effektiver Zugriff zeigt die tatsächlich vorhandenen Rechte eines Benutzers/einer Gruppe. - Rechte möglichst an Gruppen vergeben (vereinfacht Verwaltung und Zuweisung an neue Benutzer).
# Rechte verweigern
---
- Verweigern (Deny) überstimmt Zulassen (Allow). - Verweigerung ist selten nötig; oft genügt einfaches Nicht-Vergeben eines Rechts.
# Effektive NTFS‑Rechte
---
- Effektive Rechte entstehen aus der Addition von Benutzer-, Gruppen- und geerbten Rechten.
- Dateirechte überschreiben Verzeichnisrechte. 
- Verweigerte Rechte überschreiben vergebene Rechte.
# Administratoren
---
- Windows‑Explorer läuft standardmäßig nicht mit Administratorrechten; deshalb sind Administratorrechte im Explorer manchmal nicht wirksam. 
- Lösung: Eingabeaufforderung als Administrator starten oder alternativen Dateimanager verwenden.
# Verhalten beim Kopieren / Verschieben
---

| Aktion                                                         | Auswirkung auf die Rechte                                                               |
| -------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Kopieren auf demselben Laufwerk oder auf anderes NTFS‑Laufwerk | Datei wird wie neu angelegt behandelt; der kopierende Benutzer wird Besitzer der Kopie. |
| Verschieben im gleichen NTFS‑Laufwerk                          | Rechte bleiben erhalten; der ausführende Benutzer wird Besitzer.                        |
| Kopieren oder Verschieben auf ein FAT‑Laufwerk                 | NTFS‑Rechte gehen verloren.                                                             |
| Verschieben auf ein anderes NTFS‑Laufwerk                      | Rechte des Zielverzeichnisses werden geerbt; ausführender Benutzer wird Besitzer.       |
Hinweise: Verhalten mit Maus vs. Befehl kann wirken wie Kopieren/Verschieben; in allen Fällen sind die direkt vergebenen Rechte der ursprünglichen Datei Ausgangspunkt, nicht die geerbten Rechte.