---
Fach:
Thema:
  - "[[KI]]"
---
Der LM Head entscheidet am Ende des Prozesses welches Token aus den Ergebnissen verwendet wird. Dazu gibt es verschiedene Strategien.
# Strategien von LM Heads
**Classification Head:** 
Für Text Klassifikation in Verbindung mit einer voll verknüpften Ausgangschicht eines Neuronalen Netzes und einer softmax Aktivierungsfunktion 

**Regression Head:** 
Für Regressionsaufgaben zur Darstellung einer kontinuierlichen Zahl ohne Aktivierungsfunktion 

**Token Classification Head**: Für die Kennzeichnung von Wortarten wird normalerweise ein Klassifikator auf Token-Ebene hinzugefügt, um jedem Token in der Eingabesequenz Bezeichnungen zuzuweisen. 

**Sequence-to-Sequence Head:** Für Aufgaben wie Übersetzung oder Zusammenfassung kann ein Decoder-Mechanismus hinzugefügt werden, um eine Token-Sequenz als Ausgabe zu generieren.

