---
Thema:
  - "[[BSI Grundschutz]]"
Fach: "[[ITS]]"
---
**Ziel** der Schutzbedarfsfeststellung ist es, diese Fragen zu klären und damit die Festlegung der Sicherheitsanforderungen und die Auswahl angemessener Sicherheitsmaßnahmen für die einzelnen Zielobjekte des betrachteten Informationsverbundes zu steuern.
# [4.1 Grundlegende Definitionen](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_4_Schutzbedarfsfeststellung/Lektion_4_01/Lektion_4_01_node.html)
## Grundwerte
Verletzung der Grundwerte liegt vor wenn:
- vertrauliche Informationen unberechtigt zur Kenntnis genommen oder weitergegeben werden (Verletzung der **Vertraulichkeit**),
- die Korrektheit der Informationen und der Funktionsweise von Systemen nicht mehr gegeben ist (Verletzung der **Integrität**),
- autorisierte Benutzer am Zugriff auf Informationen und Systeme behindert werden (Verletzung der **Verfügbarkeit**).
## Schadensszenarien
- Verstöße gegen **Gesetze**, **Vorschriften** oder **Verträge**
- Beeinträchtigungen des informationellen **Selbstbestimmungsrechts**
- Beeinträchtigungen der **persönlichen Unversehrtheit**
- Beeinträchtigungen der **Aufgabenerfüllung**
- negative **Innen**- oder **Außenwirkung**
- **finanzielle** Auswirkungen.
# [4.2 Schutzbedarfskategorien](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_4_Schutzbedarfsfeststellung/Lektion_4_02/Lektion_4_02_node.html)
Aufgrund von **Schadensszenarien** und **Beeinträchtigung der Aufgabenerfüllung** werden die Kriterien für den Schutzbedarf festgelegt.

- **normal:** Die Schadensauswirkungen sind begrenzt und überschaubar.
- **hoch**: Die Schadensauswirkungen können beträchtlich sein.
- **sehr hoch**: Die Schadensauswirkungen können ein existentiell bedrohliches, katastrophales Ausmaß erreichen.

**Beispiel**
**Normaler** Schutzbedarf:
- „Der mögliche finanzielle Schaden ist kleiner als 50.000 Euro.“
- „Die Abläufe bei RECPLAST werden allenfalls unerheblich beeinträchtigt. Ausfallzeiten von mehr als 24 Stunden können hingenommen werden.“

**Hoher** Schutzbedarf:
- „Der mögliche finanzielle Schaden liegt zwischen 50.000 und 500.000 Euro.“
- „Die Abläufe bei RECPLAST werden erheblich beeinträchtigt. Ausfallzeiten dürfen maximal 24 Stunden betragen.“

**Sehr hoher** Schutzbedarf:
- „Der mögliche finanzielle Schaden liegt über 500.000 Euro.“
- „Die Abläufe bei RECPLAST werden so stark beeinträchtigt, dass Ausfallzeiten, die über zwei Stunden hinausgehen, nicht toleriert werden können.“
# [4.3 Vorgehen und Vererbung](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_4_Schutzbedarfsfeststellung/Lektion_4_03/Lektion_4_03_node.html)
Bei der **Vererbung** lassen sich, am Beispiel von IT-Systemen veranschaulicht, **folgende Fälle** unterscheiden:
- In vielen Fällen lässt sich der höchste Schutzbedarf aller Anwendungen, die das IT-System benötigen, übernehmen (**Maximumprinzip**).
- Wenn eine Anwendung auf die Ergebnisse einer anderen Anwendung angewiesen ist, überträgt sich ihr Schutzbedarf auf diese liefernde Anwendung. Werden diese beiden Anwendungen auf verschiedenen IT-Systemen ausgeführt, dann muss auch der Schutzbedarf des einen auf das liefernde System übertragen werden (**Betrachtung von Abhängigkeiten**).
- Der Schutzbedarf des IT-Systems kann höher sein als der Schutzbedarf der einzelnen Anwendungen (**Kumulationseffekt**). Dies ist z. B. der Fall, wenn auf einem Server mehrere Anwendungen mit normalem Schutzbedarf betrieben werden. Der Ausfall einer dieser Anwendungen könnte überbrückt werden. Wenn aber alle Anwendungen gleichzeitig ausfallen, kann ein hoher Schaden entstehen.
- Der Schutzbedarf kann niedriger sein als der Schutzbedarf der zugeordneten Anwendungen, wenn eine Anwendung mit hohem Schutzbedarf auf mehrere Systeme verteilt ist und auf dem betreffenden IT-System nur weniger wichtige Teile dieser Anwendung ausgeführt werden (**Verteilungseffekt**). Bei Anwendungen, die personenbezogene Daten verarbeiten, sind z. B. Komponenten weniger kritisch, in denen die Daten nur in pseudonymisierter Form verwendet werden.
# [4.4 Schutzbedarfsfeststellung für Prozesse und Anwendungen](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_4_Schutzbedarfsfeststellung/Lektion_4_04/Lektion_4_04_node.html)
Dabei kann es Ihnen helfen, **„Was wäre wenn ...?“-Fragen** zu jedem Schadensszenario zu formulieren, z. B. was wäre, wenn geheime Geschäftsdaten aus der Anwendung „Finanzbuchhaltung“ bekannt würden?
- Gegen welche Gesetze oder Vorschriften wird verstoßen? Welche rechtlichen Konsequenzen oder Sanktionen können mit dem Vorfall verbunden sein?
- Gibt es Personen, deren informationelles Selbstbestimmungsrecht beeinträchtigt wird? Wenn ja, mit welchen Folgen?
- Wie stark werden Abläufe in der Firma behindert?
- Droht ein Image-Schaden und mit welchen Folgen wäre er verbunden?
- Kann dieser Vorfall finanzielle Auswirkungen haben und falls ja, in welcher Höhe?

**Beispiel**

| Bezeichnung und Beschreibung | Schutzziel und Schutzbedarf           | Begründung                                                                                                                                                                                             |
| ---------------------------- | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| A010 Active Directory        | Vertraulichkeit:  <br>**normal**      | Passwörter sind verschlüsselt gespeichert und damit praktisch nicht zugänglich                                                                                                                         |
|                              | Integrität:  <br>**hoch**             | Alle Mitarbeiter identifizieren sich mit Passwörtern, daher ist der Schutzbedarf hoch.                                                                                                                 |
|                              | Verfügbarkeit:  <br>**sehr** **hoch** | Bei Ausfall des Authentisierungssystems können Mitarbeiter sich nicht identifizieren; eine Ausführung von IT-Verfahren ist dann nicht möglich. Ein Ausfall von mehr als 2 Stunden ist nicht tolerabel. |
# [4.5 Schutzbedarfsfeststellung für IT-Systeme](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_4_Schutzbedarfsfeststellung/Lektion_4_05/Lektion_4_05_node.html)
**Beispiel**

| Bezeichnung und Beschreibung | Schutzziel und Schutzbedarf    | Begründung                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ---------------------------- | ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| S007 Virtualisierungsserver  | Vertraulichkeit:  <br>**hoch** | _Maximumprinzip_:  <br>Der Domain Controller beinhaltet das Active Directory und damit die Anmeldeinformationen aller Mitarbeiter.                                                                                                                                                                                                                                                                                                                            |
|                              | Integrität:  <br>**hoch**      | _Maximumprinzip_:  <br>Der Dateiserver verwaltet Dateien, deren Korrektheit für den Geschäftsbetrieb sichergestellt sein muss.                                                                                                                                                                                                                                                                                                                                |
|                              | Verfügbarkeit:  <br>**hoch**   | _Kumulationseffekt_:  <br>Sowohl der Domain Controller als auch der Dateiserver haben jeder (sehr) hohe Verfügbarkeitsanforderungen. Daraus ergibt sich für den Virtualisierungsserver ein sehr hoher Schutzbedarf.  <br>Alle virtualisierten Systeme können aber innerhalb kurzer Zeit auf dem anderen Virtualisierungsserver zur Verfügung gestellt werden. Durch diesen _Verteilungseffekt_ reduziert sich der Schutzbedarf auf ein nur noch hohes Niveau. |
# [4.6 Schutzbedarfsfeststellung für Räume](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_4_Schutzbedarfsfeststellung/Lektion_4_06/Lektion_4_06_node.html)
Bei der Schutzbedarfsfeststellung für Räume berücksichtigen Sie alle Räume und Liegenschaften, die Sie zuvor in der Strukturanalyse identifiziert haben und die für die Informationen, Anwendungen und IT-Systeme des betrachteten Informationsverbundes relevant sind.

**Beispiel**

| Bezeichnung | Art        | Lokation | IT-System                        | Vertraulichkeit | Integrität | Verfügbarkeit |
| ----------- | ---------- | -------- | -------------------------------- | --------------- | ---------- | ------------- |
|             |            |          |                                  |                 |            |               |
| BG, R. 1.02 | Serverraum | GB1      | N001 bis N004  <br>S001 bis S007 | Hoch            | Hoch       | Hoch          |
# [4.7 Schutzbedarfsfeststellung für Kommunikationsverbindungen](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/Zertifizierte-Informationssicherheit/IT-Grundschutzschulung/Online-Kurs-IT-Grundschutz/Lektion_4_Schutzbedarfsfeststellung/Lektion_4_07/Lektion_4_07_node.html)
Sie sollten folgende **Verbindungen** als **kritisch** einstufen:
- Verbindungen, die aus dem Unternehmen oder der Behörde **in ein öffentliches Netz** (z. B. Telefonnetz, Internet) oder **über ein öffentliches Gelände** reichen. Über solche Verbindungen können Schadprogramme in das Datennetz der Institution eingeschleust werden, Server der Institution angegriffen werden oder Mitarbeiter ver­trauliche Daten an Unbefugte weiterleiten.
- Verbindungen, über die besonders **schützenswerte Informationen** übertragen werden. Mögliche Gefährdungen sind Abhören, vorsätzliche Manipulation und betrügerischer Missbrauch. Vom Ausfall solcher Verbindungen sind Anwendungen, für die eine hohe Verfügbarkeit erforderlich ist, besonders betroffen.
- Verbindungen, über die vertrauliche Informationen **nicht übertragen werden dürfen**. Personaldaten dürfen zum Beispiel nur von Mitarbeitern der Personalabteilung und der Geschäftsführung eingesehen und bearbeitet werden. Daher muss verhindert werden, dass diese Daten bei ihrer Übertragung von unbefugten Mitarbeitern eingesehen werden können.

**Beispiel**

|Verbindung|Vertraulichkeit|Integrität|Verfügbarkeit|
|---|---|---|---|
|K001: Firmennetz – Internet|**Hoch:**  <br>Vertrauliche Informationen können z. B. an den Wettbewerb gelangen|**Hoch:**  <br>Falsche Informationen können den Ruf schädigen.|**Hoch:**  <br>Ohne diese Außenverbindung kann keine Kommunikation stattfinden.|