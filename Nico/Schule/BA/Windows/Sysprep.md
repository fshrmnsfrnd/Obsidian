---
Fach: "[[BA]]"
Thema:
  - "[[Microsoft]]"
  - "[[Windows Client]]"
  - "[[Schule/BA/Windows Server/Windows Server|Windows Server]]"
---
Sysprep bereitet ein Windows-System für das Klonen vor und erzeugt beim ersten Start nach einem Sysprep-Lauf eine neue System-SID; daraus folgen neue SIDs für lokale Benutzer und Gruppen; Administratorpasswort und benutzerspezifische Daten werden gelöscht, während Benutzerkonten, Treiber und installierte Programme erhalten bleiben; beim ersten Neustart muss jedoch ein neuer Benutzer angelegt werden.  
# GUI und Standardoptionen
---  
Die grafische Anwendung liegt unter `C:\Windows\System32\Sysprep\Sysprep.exe`. Wichtige Standardoptionen:  
- Out-of-Box-Experience aktivieren: führt beim nächsten Start die letzten Installationsschritte aus (u.a. Aktivierungsschlüssel eingeben, Benutzer anlegen).  
- Verallgemeinern: erzeugt eine neue SID.  
- Herunterfahren: fährt den Rechner nach Sysprep herunter.  
# Alternative Betriebsmodi
---  
- Systemüberwachungsmodus (Audit Mode): für Händler, die nach Sysprep einzelne Rechner weiterhin mit Programmen/Treibern anpassen möchten.  
- Verhalten nach Sysprep kann statt Herunterfahren auch Neustart oder einfaches Beenden sein.  
# Häufige Probleme und Einschränkungen
---  
- Bestimmte Programme (insbesondere Virenscanner) können geklonte Installationen am ordnungsgemäßen Start hindern; Lösung: betroffene Software nachträglich installieren.  
- UWP-Apps sind kritisch: unterschiedliche Apps oder Versionen zwischen Benutzern führen oft zu Problemen nach Sysprep.  
- Auf Windows Servern können einige Serverrollen nach Sysprep nicht mehr korrekt funktionieren.  
# Sysprep und Windows-Aktivierung
---  
- Windows kann ohne Aktivierung installiert werden (z.B. Windows 10 Enterprise: 90 Tage Evaluierungszeitraum).  
- Der Evaluierungszeitraum lässt sich bei manchen Editionen ein- bis dreimal mit `slmgr -rearm` zurücksetzen (als Administrator ausführen).  
- Ein Sysprep-Lauf entfernt eine vorhandene Aktivierung und verbraucht eine der maximal drei Rücksetzmöglichkeiten.