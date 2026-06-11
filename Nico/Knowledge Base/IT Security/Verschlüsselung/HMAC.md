---
Fach: "[[ITS]]"
Thema:
  - "[[Security]]"
---
**Hash-Based Message Authentication Code**

Mit HMAC können Sie eine Authentisierung durchführen und mithilfe geheimer Keys verifizieren, dass Daten korrekt und authentisch sind – eine Alternative zu Verfahren, die [[Signaturen]] und asymmetrische Kryptografie verwenden.

# Funktionsweise
---
HMAC-Keys bestehen aus zwei Komponenten. Diese sind:
1. **Kryptografische Keys.** Die Daten werden über einen Verschlüsselungsalgorithmus modifiziert. Anschließend benötigt der Empfänger einen speziellen Code (oder Schlüssel), um die Informationen wieder lesbar zu machen. HMAC basiert auf einem geteilten Satz geheimer Schlüssel.
2. **Hash-Funktion.** Ein Hash-Algorithmus verändert oder verarbeitet die Nachricht noch einmal. HMAC verwendet generische kryptografische Hash-Funktionen wie SHA-1 oder MD5

Zwei Teilnehmer, die das System nutzen wollen, müssen sich vorab also auf zwei Dinge einigen:
- **Geheime Keys.** Sie müssen in der Lage sein, die Nachrichten, die sie empfangen, zu entschlüsseln. Dies geschieht mithilfe eines geheimen Keys, der vertraulich und verborgen bleibt.
- **Einen Algorithmus.** Sie müssen eine Hash-Funktion wählen, durch die alle ihre Nachrichten geleitet werden.

![[Pasted image 20251215153446.png]]