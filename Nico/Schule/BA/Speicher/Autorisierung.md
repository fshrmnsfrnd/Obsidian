---
tags:
Fach: "[[BA]]"
Thema:
  - "[[Security]]"
---
>Jedes sicherungsfähige Objekt (Laufwerk, Ordner, Datei, …) kann einen Security-Descriptor haben, der festlegt, wer wie auf dieses Objekt zugreifen darf.

Der SD (Security Descriptor) enthält:
- SID des Besitzers
- DACL (Discretionary Access Control List)
- SACL (System Access Control List)

### ACE (Access Control Entry)
- Trustee (Benutzer oder Gruppe) 
- ACEType (Allow / Deny) 
- ACEFlags (vererben an) 
	- Diesen Ordner 
	- Unterordner 
	- Dateien 
- ACEMask (Rechte) 
	- lesen 
	- schreiben
	- ...

# Konsolentools
**icacls** zum lesen und ändern von NTFS Berechtigungen

## Grundlegende Berechtigungen 
| Symbol | Grundlegende Berechtigung                | Symbol bei Konvention |
| ------ | ---------------------------------------- | --------------------- |
| F      | Vollzugriff                              | V                     |
| M      | Ändern                                   | LS                    |
| RX     | Lesen, Ausführen (Ordnerinhalt anzeigen) | L                     |
| R      | Lesen                                    |                       |
| W      | Schreiben                                |                       |

## Erben von oben 
|Symbol |Vererbung|
|-|-|
|(I) |geerbt vom übergeordneten Verzeichnis |

## Vererben an 
| Symbol | Berechtigungen gelten für                                                                |
| ------ | ---------------------------------------------------------------------------------------- |
| (OI)   | Dateien                                                                                  |
| (CI)   | Unterordner                                                                              |
| (IO)   | diesen Ordner nicht (erbt nur von oben)                                                  |
| (NP)   | nur für Ordner und Dateien in diesem Ordner, werden aber nicht weiter nach unten vererbt |


## Lesen
`icacls <PATH>`

PS: `Get-ACL <PATH>`

## Schreiben
`icacls <PATH> /grant <USER>:Privileges`