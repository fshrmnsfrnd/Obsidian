---
Fach: "[[BA]]"
Thema:
  - "[[Microsoft]]"
  - "[[Schule/BA/Windows Server/Windows Server|Windows Server]]"
---
# Dashboard (Server‑Manager)
- Kacheln zeigen wichtige Funktionen; Grün bedeutet nur: Dienst läuft — nicht zwingend: Dienst funktioniert korrekt.
- Beispiel: Ein gestarteter DHCP-Server kann trotzdem keine Adressen verteilen; die Kachel bleibt grün.
- Kacheln werden meist nur rot, wenn der Best Practices Analyzer (BPA) Probleme meldet.
# Lokaler Server & Dienste
- Die Kachel „Lokaler Server“ ist häufig rot.
- Die Zeile „Dienste“ fasst Hintergrunddienste zusammen, die keinen eigenen Bereich haben.
- Klick in der Kachel auf „Dienste“, um problematische Dienste aufzulisten.
- Nach einem Neustart können verzögert startende Dienste kurz als „Beendet“ erscheinen — meist unkritisch; bei Bedarf manuell starten.
- Unwichtige Dienste (z. B. Karten‑Manager, Shell‑Hardwareerkennung auf fernverwalteten Servern) lassen sich per Auswahlfeld von der Überwachung ausschließen.
# Leistungsindikatoren
- Zeigen Auslastung von CPU und Arbeitsspeicher.
- Sie können Warnungen konfigurieren, wenn Grenzwerte überschritten werden.
- Aktuellen Leistungsstatus finden Sie unter „Lokaler Server“ oder „Alle Server“ → Abschnitt „Leistung“.
# Best Practices Analyzer (BPA)
- Prüft Serverkonfiguration auf Fehler und Abweichungen von Microsoft‑Empfehlungen.
- Starten Sie vor dem BPA die Leistungsindikatoren für den jeweiligen Server.
- BPA starten: Bereich „BEST PRACTICES ANALYZER“ → „AUFGABEN“.
- Ergebnisse erscheinen im Dashboard unter „BPA‑Ergebnisse“ (Anzeige kann etwas dauern).
- Nicht gewünschte BPA‑Meldungen lassen sich im Kontextmenü der Fehlermeldung ausschließen.
# Ereignisanzeige
- Protokolliert wichtige Aktionen und Informationsmeldungen (z. B. behobene Fehler).
- Zu finden im Server‑Manager unter „Tools“ → „Ereignisanzeige“.
- Die Zusammenfassung der administrativen Ereignisse oben bietet einen schnellen Überblick.
- Kritische Ereignisse erfordern meist Eingreifen; prüfen Sie bei Fehlern zuerst, ob sie noch aktuell sind.
# Expertenaufgabe
- Auf Domänencontroller: Kommando dcdiag ausführen und Ausgabe lesen.
- Ein fehlerfreies Durchlaufen aller Tests ist meist erst ~24 Stunden nach Serverstart zu erwarten.