---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
>Constraints sind Regeln, die Ausrichtung und den Abstand eines Widgets oder [[Views]] zu anderen Widgets oder [[Views]] festlegen. Constraints bestimmen die Reaktion der Benutzeroberfläche, auf Änderung der Geräteausrichtung oder bei der Anzeige auf anderen Geräten mit unterschiedlichen Bildschirmgrößen.

**Vorteile:**
Das Constraint-Layout ist so flexibel, dass Benutzeroberflächen, für die früher mehrere Layouts verschachtelt werden mussten, einfach zu erstellen sind. Das führt zu weniger komplexen Layouts und zu einer verbesserten Leistung zur Laufzeit. Zusätzlich erleichtert das Constraint-Layout die Entwicklung von Benutzeroberflächen im Hinblick auf die große Bandbreite von Android-Geräten, die heute auf dem Markt erhältlich sind.
# Ränder (Margins)
---
Jeder Verbindung wird ein fester Abstandswert zugeordnet. Dieser Rand legt den Abstand fest zwischen dem View und einem anderen View fest.
![[Pasted image 20260214140756.png]]
- keine Flexibilität bei Drehung under unterschiedlicher Bildschirmgröße
# Entgegengesetzte Einschränkungen (Opposing Constraints)
---
Zwei Constraints, die entlang derselben Achse auf einem View/Widget wirken, werden als entgegengesetzte Constraints bezeichnet.
![[Pasted image 20260214140941.png]]
- Hier werden prozentuale Werte verwendet
- Ist flexibel bei unterschiedlicher Bildschirmgröße
# Verschiebung (Constraint Bias)
---
Sind alle entgegengesetzten Constraints eines [[Views]] - horizontal und vertikal - gleich lang, wird der View innerhalb des Constraint-Layout zentriert (siehe Abbildung 2). Beim horizontalen oder vertikalen Verschieben des [[Views]] werden die Ränder entsprechend angepasst. Man spricht von einer horizontalen bzw. vertikalen Verschiebung (bias).
![[Pasted image 20260214141203.png]]
# Ketten (Chains)
---
Ketten bieten eine Möglichkeit, zwei oder mehreren [[Views]] als Gruppe zu verbinden und ihr Layout-Verhalten festzulegen. Es gibt horizontale und vertikale Ketten. Verkettete [[Views]] sind durch bidirektionale Constraints miteinander verbunden.
![[Pasted image 20260214141309.png]]
Der erste View in der Kette ist der Kettenkopf; in einer vertikalen ist das der oberste View, oder im Fall einer horizontalen Kette der View ganz links. Das Layout-Verhalten der gesamten Kette wird in erster Linie durch die Einstellung von Attributen für das Kettenkopf-Widget konfiguriert.
## Chain Styles
### Spread Chain
![[Pasted image 20260214141432.png]]
### Spread Inside Chain
![[Pasted image 20260214141445.png]]
### Weighted Chain
![[Pasted image 20260214141501.png]]
### Packed Chain
![[Pasted image 20260214141531.png]]
# Ausrichtung nach Inhalt von Widgets (baseline constraint)
---
Diese Art der Ausrichtung verwendet den Inhalt der einzelnen [[Views]] als Ausrichtungslinie
![[Pasted image 20260214141629.png]]
# Größenanpassung eines Widgets
---
**fixed**: Das Widget wird auf die angegebenen Abmessungen festgelegt 
**match constraint**: Ermöglicht die Größenanpassung des Widgets durch die Layout-Engine, um die eingestellten Bedingungen zu erfüllen. 
**Wrap Content**: Die Größe des Widgets richtet sich nach seinem Inhalt. 
# Hilfslinien (guidelines) 
---
Hilfslinien sind spezielle Elemente, die innerhalb des Constraint-Layouts verfügbar sind. Es können mehrere Hilfslinien zu einer Constraint-Layout hinzugefügt werden. Eine Hilfslinie kann entweder horizontal oder vertikal verlaufen. Ein Widgets kann über Contraints mit einer Hilfslinie verbunden werden. Dies ist besonders nützlich, wenn mehrere Widgets entlang einer Achse ausgerichtet werden müssen.
![[Pasted image 20260214141747.png]]
# Gruppen (groups) 
---
Diese Funktion von Constraint-Layout ermöglicht es, Widgets zu logischen Gruppen zusammenzufassen. Diese Gruppen können dann wie eine Einheit konfiguriert werden. 

Eine Gruppe ist im Wesentlichen eine Liste von Verweisen auf die enthaltenen Widgets eines Layouts. Einstellungen auf Gruppenebene werden an alle Gruppenmitglieder weitergegeben. Dadurch ist es möglich z.B. eine Gruppe von Widgets mit einer Attribut-Änderung ein- bzw. auszublenden. 

Ein einzelnes Constraint-Layout kann mehrere Gruppen enthalten und ein Widget kann zu mehr als einer Gruppe gehören. Wenn ein Konflikt zwischen Gruppen auftritt, hat die zuletzt in der XML-Datei deklarierte Gruppe Vorrang.
# Barrieren (Barriers)
---
**Problem:**
![[Pasted image 20260214141909.png]]
**Lösung**
![[Pasted image 20260214142011.png]]

# Flow (Flow)
---
Ein Flow zeigt die zugeordneten Widgets in einem fließenden Rasterlayout an. Ein Flow enthält Verweise auf die Widgets, für deren Verwaltung er verantwortlich ist. Ein Flow bietet eine Vielzahl von Konfigurationsoptionen:
- Positionierung
- vertikaler und horizontaler Ausrichtung
- Umbruchverhalten
- Abstand und Ausrichtungseigenschaften
- Die Chain-Styles: spread, spread inside und packed können auch bei einem Flow eingesetzt werden
## Flow Beispiele
### Horizontaler Flow
![[Pasted image 20260214142316.png]]
### Horizontaler Flow (n Widgets per Line)
![[Pasted image 20260214142329.png]]
### Horizontaler Flow n Widgets per Line (with Gap)
![[Pasted image 20260214142348.png]]
### Ganz wild
horizontaler Flow aus beliebig breiten Widgets, nur 3 Widgets pro Zeile, horizontal-bias = 1.0 (links-bündig: horizontal-bias = -1.0, zentriert: horizontal-bias = 0.0, rechts-bündig: horizontal-bias = 1.0)
![[Pasted image 20260214142404.png]]