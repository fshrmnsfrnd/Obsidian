---
Fach: "[[BA]]"
Thema:
  - "[[Microsoft]]"
  - "[[Windows Client]]"
---
# Installationsmedien & Editionen
---
- DVDs mit "x86" enthalten die 32‑Bit‑Version, mit "x64" die 64‑Bit‑Version von Windows 10.  
- Editionen (Kurzüberblick):
  - Windows 10 Home: für Heimanwender; kein Hyper‑V, kein BitLocker.
  - Windows 10 Pro: für Firmenkunden.
  - Windows 10 Enterprise: Firmenversion mit allen Funktionen (z. B. AppLocker).
  - Windows 10 Education: Enterprise‑Funktionen für Bildungseinrichtungen.
  - N‑Editionen (EU): ohne Windows Media Player.
- Manche Installationsmedien enthalten mehrere Editionen; die Wahl erfolgt über den Aktivierungsschlüssel (oder manuell).
# Funktionsupdates (Upgrades)
---
- Microsoft liefert keine komplett neuen Windows‑Versionen mehr, sondern zweimal jährlich Feature‑Updates.
- Alte Installationsmedien erhalten fehlende Neuerungen per Windows Update (Internetverbindung nötig).
- Eine nicht auf dem neuesten Funktionsstand gehaltene Installation verliert nach einiger Zeit auch Sicherheitsupdates (Ausnahme: Langzeitunterstützte / LTSC‑Versionen).
- Unterrichts‑Basis: Windows 10 Education Version 21H2 (Ausgabe 2. Hj. 2021).
# Virtuelle Maschine für den Unterricht
---
- Sie erhalten eine VirtualBox‑VM mit bereits größtenteils installiertem Windows (schnellerer Installationsablauf).
- VirtualBox‑Gasterweiterungen sind bereits eingerichtet.
- Standard‑RAM: 2048 MB. Empfehlung: auf 4096 MB erhöhen, wenn Host genügend RAM hat.
- Vor dem ersten Start: virtuelle Netzwerkverbindung trennen (wird im Unterricht gemeinsam gemacht).
# Sprachsteuerung (Cortana)
---
- Cortana ist im Unterricht nicht erforderlich; Aktivierung bleibt Ihnen überlassen.
# Updates & Netzwerkverbindung während Installation
---
- Windows lädt während der Installation Updates; sinnvoll für Sicherheit, aber zeitaufwändig.
- Für den Unterricht: Installation in einer VM ohne Netzwerkverbindung.  
  - Beim Netzwerkeinrichtungs‑Schritt: Link links unten "Ich habe kein Internet" anklicken, um die Einrichtung zu überspringen.  
  - Auf dem folgenden Bildschirm erneut den Link links unten benutzen, falls eine Netzwerkverbindung verlangt wird.  
  - ![[Pasted image 20260312173214.png]]
# Benutzerkonto
---
- Hinweis: Bei vorhandener Internetverbindung bietet Windows die Anmeldung mit einem Microsoft‑Konto an. Seit Version 2004 ist es nicht mehr möglich, bei funktionierender Internetverbindung während der grafischen Installation einen lokalen Benutzer anzulegen.  
  -  ![[Pasted image 20260312173241.png]]
# Sicherheitsfragen
---
- Nach Passwort verlangt Windows drei Sicherheitsfragen zur Wiederherstellung.
- Da die Antworten oft recherchierbar sind, wird empfohlen, für alle drei Fragen jeweils ein wirres, zufälliges Zeichen‑Durcheinander einzutragen (sicherer als reale Antworten).  
  -  ![[Pasted image 20260312173336.png]]
# Kurzanleitung (Checkliste)
---
- PC starten, Installationsschritte durchlaufen.  
- Bei Netzwerkanfrage: "Ich habe kein Internet" (links unten) wählen.  
- Benutzer adminlokal2 mit Passwort Kennwort1 anlegen.  
- Sicherheitsfragen mit zufälligen Zeichen beantworten.  
- RAM der VM bei Bedarf von 2048 MB auf 4096 MB erhöhen.