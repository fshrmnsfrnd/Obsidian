---
Fach: "[[Berufsschule]]"
Thema:
  - "[[Hardware]]"
---
# SSD VS HDD

| |**SSD**|**HDD**|
|---|---|---|
|Vorteile|- Schnellere Lese / Schreibgeschwindigkeit  <br>- 4x Schneller  <br>- Keine mechanischen Teile, die kaputt gehen können  <br>-> stoßfest  <br>- Leicht  <br>- Klein (kompakt)  <br>- Geräuschlos  <br>- Geringer Stromverbrauch  <br>- weniger Wärmeverluste|- 3 bis 4 mal günstiger bezogen auf die Speicherkapazität|
|Verwendungszweck|- Für Anwendungen  <br>- VMs  <br>- Betriebssysteme|- Wenn man viel Speicherplatz braucht für Dateien|

# SSD (Solid State Drive)
---
## Kenngrößen und Fachbegriffe:

|**Größe**|**Bescheibung**|
|---|---|
|- S-ATA 3 (6 Gbit/s)  <br>- SAS (12 Gbit/s)  <br>- FC (8 Gbit/s)  <br>- PCIe (16 Gbit/s)  <br>- M.2|Schnittstellenstandards|
|- 1"  <br>- 1,8"  <br>- 2,5"  <br>- 3,5"|Formfaktoren|
|>=0,025ms|Zugriffszeit|
|0,1 W (Ruhe) - 5 W (Zugriff)|Leistungsverbrauch|
|Wear Leveling|- Gleichmäßige Verteilung der Schreibvorgänge auf Speicherzellen  <br>- Merken der Anzahl der Schreibzyklen auf Speicherzelle (weicht aus falls nötig)|
|GC|**G**arbage **C**ollection  <br>- jede Speicherzelle muss vor dem Überschreiben gelöscht werden (kostet Zeit)  <br>- Nutzung von Leerlaufzeit um Speicherzellen vorzubereiten  <br>- Wenn OS Dateien löscht wird ein TRIM-Befehl benötigt, damit die SSD das weiß|
|- SLC  <br>- MLC  <br>- TLC|- **S**ingle **L**evel **C**ell (ein Bit in einer Zelle)  <br>- **M**ulti Level Cell (zwei Bit in einer Zelle)  <br>- **T**ripel **L**evel **C**ell (drei Bit in einer Zelle)|
|IOPS|**I**nput **O**utput (Operationen) **P**er **S**ekunde|
|MTBF|**M**ean **T**ime **B**etween **F**ailures (Zeitraum bis ein Fehler auftritt)|
|Trim|gelöschte Daten werden markiert und zu einem anderem Zeitpunkt gelöscht|
|S.M.A.R.T.-Unterstützung|**S**elf-**M**onitoring, **A**nalysis and **R**eporting **T**echnology|
|TBW|**T**erra**B**ytes **W**ritten (Bereits geschriebene Terrabytes)|
## Bestandteile einer SSD:
![[ncxa-ksvjV-700.webp]]