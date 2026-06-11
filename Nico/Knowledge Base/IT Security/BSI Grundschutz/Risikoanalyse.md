---
Fach: "[[ITS]]"
Thema:
  - "[[BSI Grundschutz]]"
---
[Kapitel 7: Risikoanalyse](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_7_Risikoanalyse/Lektion_7_node.html) 
[Elementare Gefährdungen](https://www.bsi.bund.de/SharedDocs/Downloads/DE/BSI/Grundschutz/IT-GS-Kompendium/Elementare_Gefaehrdungen.pdf?__blob=publicationFile&v=4)
# Wann macht man eine Risikoanalyse? (Zielobjekte)
---
Eine Risikoanalyse muss nicht für alle Objekte durchgeführt werden.
**Zielobjekte** für eine Risikoanalyse könnten sein:
- Objekte mit einem sehr **hohen Schutzbedarf** in einem der **drei Grundwerte** (Vertraulichkeit, Integrität, Verfügbarkeit)
- Objekte mit **keinem passenden IT-Grundschutzbaustein**
- **Untypische** Einsatzszenarien
# Einschätzung von Gefährdungen
---
### Eintrittshäufigkeit
|Eintrittshäufigkeit|Beschreibung|
|---|---|
|selten|Das Ereignis könnte nach heutigem Kenntnisstand höchstens alle fünf Jahre auftreten.|
|mittel|Das Ereignis tritt einmal alle fünf Jahre bis einmal im Jahr ein.|
|häufig|Das Ereignis tritt einmal im Jahr bis einmal pro Monat ein.|
|Sehr häufig|Das Ereignis tritt mehrmals im Monat ein.|
### Schadenshöhe

|Schadenshöhe|Schadensauswirkungen|
|---|---|
|vernachlässigbar|Die Schadensauswirkungen sind gering und können vernachlässigt werden.|
|begrenzt|Die Schadensauswirkungen sind begrenzt und überschaubar.|
|beträchtlich|Die Schadensauswirkungen können beträchtlich sein.|
|existenzbedrohend|Die Schadensauswirkungen können ein existenziell bedrohliches, katastrophales Ausmaß annehmen.|
### Zweck der Einschätzung
- Grundlage, um:
	- Risiken priorisieren zu können
	- zu entscheiden, wo Maßnahmen am dringendsten sind
	- zu bewerten, ob Rest-Risiko akzeptabel ist
# Risikomatrix
---
![[Pasted image 20260312125008.png]]
- Achsen:
	- X-Achse: Eintrittswahrscheinlichkeit / -häufigkeit
	- Y-Achse: Schadenshöhe  
- Jede Gefährdung wird in das Raster eingetragen  
- Ergebnis: Risikoklassen (z.B. gering, mittel, hoch, sehr hoch) durch Farbfelder  
- Nutzung:
	- Schnelle Übersicht über die kritischsten Risiken
	- Priorisierung von Maßnahmen  
# Risikobewertung
---
Es können auch mehr oder weniger Kategorien verwendet werden.
Zur Bewertung werden Eintrittshäufigkeiten und Schadensauswirkungen verwendet.

|Risikokategorie|Definition|
|---|---|
|gering|Die bereits umgesetzten oder zumindest im Sicherheitskonzept vorgesehenen Maßnahmen bieten einen ausreichenden Schutz.|
|mittel|Die bereits umgesetzten oder zumindest im Sicherheitskonzept vorgesehenen Maßnahmen reichen möglicherweise nicht aus.|
|hoch|Die bereits umgesetzten oder zumindest im Sicherheitskonzept vorgesehenen Sicherheitsmaßnahmen bieten keinen ausreichenden Schutz vor der jeweiligen Gefährdung. Das Risiko kann mit einer großen Wahrscheinlichkeit nicht akzeptiert werden.|
|sehr hoch|Die bereits umgesetzten oder zumindest im Sicherheitskonzept vorgesehenen Sicherheitsmaßnahmen bieten keinen ausreichenden Schutz vor der jeweiligen Gefährdung. Das Risiko kann mit einer sehr großen Wahrscheinlichkeit nicht akzeptiert werden.|
# Umgang mit Risiken (Behandlungsstrategien)
---
### Risikovermeidung
- Risiko vollständig ausschalten
- Beispiele:
	- Bestimmte Technik / Anwendung gar nicht einsetzen
	- Gefahrenträchtige Prozesse ganz abschaffen  
### Risikoreduktion
- Risiko verkleinern (Eintrittswahrscheinlichkeit oder Schaden)
- Beispiele:
	- Technische Maßnahmen (Firewall, Backup, Verschlüsselung)
	- Organisatorische Maßnahmen (Regeln, Schulungen, Prozesse)
	- Physische Maßnahmen (Zutrittskontrollen, Alarmanlagen)  
### Risikotransfer
- Risiko (oder Folgen) auf Dritte übertragen
- Beispiele:
	- Versicherungen (z.B. Cyber-Versicherung)
	- Outsourcing / Dienstleister mit vertraglicher Haftung  
### Risikoakzeptanz
- Risiko bewusst hinnehmen
- Voraussetzungen:
	- Risiko ist bekannt, dokumentiert und bewertet
	- Kosten der Reduktion wären höher als der erwartete Schaden
	- Management entscheidet und übernimmt Verantwortung