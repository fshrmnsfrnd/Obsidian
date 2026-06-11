---
Fach:
Thema:
  - "[[Knowledge Base/Netzwerktechnik/Switching/Switching|Switching]]"
---
Broadcast Frames können die normale Übertragung stark hemmen.

Klettert der Broadcast-Anteil beispielsweise über 20 Prozent, dann sperrt der Switch weitere Broadcasts auf dem betroffenen Port für eine kurze Frist, meist rund zehn Sekunden. Sinkt währenddessen der Broadcast-Anteil, dann lässt der Switch nach einer weiteren Karenzzeit die Broadcasts wieder passieren.

Will man bestimmte Teilnehmer oder Zweige in seinem LAN drosseln, bieten manche Geräte dafür eine mit Storm Control verwandte Technik an, die mal Rate Limiting, mal Bandwidth Control heißt. Damit kann der Admin einen maximalen Durchsatz oder eine Paketrate festlegen, die ein Port akzeptiert.