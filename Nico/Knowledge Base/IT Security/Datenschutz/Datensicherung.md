---
Thema:
  - "[[Security]]"
---
# Was ist Datensicherung?
---
**Datensicherung = Backup und/oder Archivierung**

**Datensicherung** ist das Kopieren von Daten auf ein anderes Speichermedium um dieses im Fall eines Datenverlusstes zurück zu kopieren. Diese gesicherten Daten nennt man **Sicherheitskopie** (eng. **Backup**). Die Wiederherrstellung der Originaldaten aus einer Sicherheiskopie bezeichnet man als **Datenwiederherstellung**, **Datenrücksicherung** oder **Restore.**

**Archivierung** steht für die unveränderbarkeit, langzeitige Aufbewahrung von Informationen.
# 3-2-1 Regel
---
Diese Regel bescheibt ein Optimales Backup Verfahren.  
**3** Kopien (mindestens)  
**2** Kopien auf unterschiedlichen Speichermedien  
**1** Kopie an einem entfernten Ort (remote)
# Speicherinfrastruktur
---
## Auswahlkriterien
- Schreib- und Lesegeschwindigkeit
- Zugriffszeit
- Kapazität
- Aufbewahrungszeit
- Alterungsbeständigkeit
- Kosten
## Moderne Speicherinfrastrukturen
![[ORDoCPFct7-700.webp]]
# Sicherungsverfahren
---
## Auswahl-Kriterien
**Recovery Point Objective (RPO):**
- Zu welchem Zeitpunkt vor dem Ausfall wurde eine Sicherung gemacht die benutzt werden kann?
- Maximal toleriebarer Datenverlust (Verlust von der Sicherung bis zum Unglück)

**Recovery Time Objective (RTO):**
- Welche Zeit wird benötigt um das Backup wieder herzustellen?
- Maximal tolerierbare Ausfallzeit (wie lange darf das System ausfallen/Downtime)

![[vuCkBHE_Y_-700.webp]]
## Incremental
1. Vollbackup
2. Änderungen seit dem Vortag

![[q4ZnbkfeRY-700.webp]]

|**Vorteile**|**Nachteile**|
|---|---|
|benötigt wenig Speicherplatz|benötigt viele Bänder zum Wiederherstellen (benötigt alle Bänder seit Vollbackup)|
### Syntetisches Voll-Backup

Hierbei handelt es sich um ein Backup-Server, der die inkrementellen Backups (meist über Hardlinks) zu einem neuen Vollbackup zusammenfügt.  
![[XBzX9jbgif-700.webp]]
## Reverse Incremental
1. Vollbackup
2. Änderungen werden ins Vollbackup geschrieben
3. Alte Versionen werden behalten
![[J89yDv5dzQ-700.webp]]

|**Vorteile**|**Nachteile**|
|---|---|
|es ist immer ein aktuelles Vollbackup da|kompliziertere Umsetzung|
|benötigt wenig Speicherplatz||
## Differenziell
1. Vollbackup
2. Änderungen abhängig von Vollbackup
![[moibSJoya3-700.webp]]

|**Vorteile**|**Nachteile**|
|---|---|
|es werden nur 2 Bänder zum Wiederherstellen benötigt|verbraucht viel Speicherplatz|