---
Fach: "[[ITS]]"
Thema:
  - "[[Security]]"
  - "[[Hardware]]"
---
>Hardware-Sicherheitsmodule (HSM) schützen sensible Sicherheitsinformationen vor Auslesen und Manipulation. Geheime Schlüssel verbleiben stets im Modul.

# Smartcards  
---
Chipkarten mit eigenem Prozessor, Speicher und sicherem Betriebssystem. Sie speichern Schlüssel und persönliche Daten sicher im EEPROM. Anwendung u.a. als EC- und Kreditkarten, Ausweise und Authentifikations-Token. Sicherheit durch PIN oder Fingerabdruck (besserer Datenschutz bei Vergleich direkt auf der Karte). Risiko: schwache oder wiederverwendete PINs.

# Trusted Platform Module (TPM):  
---
Kleiner Sicherheitschip nach TCG-Standard, fest in Geräte (PC, Smartphone, Router etc.) integriert. Dient zur Geräteidentifikation, Lizenz- und Datenschutz. Enthält eindeutigen kryptografischen Schlüssel, aber funktioniert meist passiv. An Computer, nicht an Benutzer gebunden.
![[Pasted image 20251117235337.png]]

# High-Level Security Module (HLSM):
---
Hochsicheres, leistungsfähiges Modul für besonders wichtige Schlüssel (z. B. Master-Keys). Erkennt Angriffe und löscht Daten automatisch. Physisch gekapselt und mit Sensorik ausgestattet. Deutlich sicherer und teurer als Smartcards. Einsatz in Banken, Industrie, Behörden, PKI-Systemen und digitalen Signaturdiensten.