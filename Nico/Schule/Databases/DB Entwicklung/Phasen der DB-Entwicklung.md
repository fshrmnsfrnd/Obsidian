---
tags:
Fach: "[[DB]]"
Thema:
  - "[[Databases]]"
---
# Anforderungs- / Informationsanalyse
---
- Festlegung der Anwendungen 
- Festlegung der Benutzergruppen 
- Ermittlung der Datenobjekte mit ihren Eigenschafen und Beziehungen 
	- Was soll gespeichert werden? 
	- Wie werden die Daten bearbeitet?
# Der konzeptionelle Entwurf
---
- Erstellung von [[ER Modell|ER-Modellen]] 
- Darstellung von [[ER Modell#Entität (Entity)|Entitäten]], mit ihren Attributen 
- Darstellung der Beziehungen zwischen Entitäten mit ihren [[Assoziationen]]. 
- Festlegung der Abfragen bzw. Views.
# Der logische Entwurf
---
- Umwandlung des E-R-Diagramms in ein relationales Datenmodell unter Anwendung der Transformations-Regeln.
- Beseitigung der Redundanzen durch [[Normalisierung]]. 
# Die Implementierung (der physische Entwurf)
---
- Die Datenbank wird erstellt. 
- Es werden SQL-Skripte erstellt, die die Tabellen und Beziehungen aus dem relationalen Datenmodell in der Datenbank anlegen. 
- Sollen Daten aus Alt-Systemen übernommen werden, müssen die Daten von dort konvertiert werden, damit sie in die neue Struktur passen. 
- Test der Ergebnisse
# Betrieb und Wartung der Datenbank
---
- Die Pflege der Daten erfolgt i. d. Regel durch die Anwendungsprogramme. 
- Bei Änderungs-Wünschen und Erweiterungen ist sind die Datenstrukturen anzupassen. 
- Bei längerem Betrieb ist möglicherweise eine Reorganisation nötig 
- Sicherungen erstellen.