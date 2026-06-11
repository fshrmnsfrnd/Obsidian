---
tags:
Fach: "[[BA]]"
Thema:
  - "[[Windows Client]]"
  - "[[Microsoft]]"
---
# Orte der Einstellungen
- Einstellungen 
	- Konten
- Systemsteuerung
	- Benutzerkonten
- MMC-Snap-In
	- lokale Benutzer und Gruppen
	- Besteht aus Modulen (Snap-Ins)
- CMD
	- `net user`
	- `net localgroup`
- PowerShell
	- Erstellen
		- `New-LocalUser 
		- `New-LocalGroup
	- Lesen 
		- `Get-LocalUser`
		- `Get-LocalGroup` 
	- Ändern 
		- `Set-LocalUser `
		- `Set-LocalGroup `
	- Löschen 
		- `Remove-LocalUser `
		- `Remove-LocalGroup`

# Gruppen
## Standardgruppen
- Können nicht verschachtelt werden
- Können User und Identitätsgruppen als Member haben
z.B. `BUILTIN/Administrators` ist eine Standardgruppe

## Spezielle Identitätsgruppen
- Diesen Gruppen werden Benutzer automatisch zugewiesen und können nicht manuell zugewiesen werden. 
- Diese Gruppen können NTFS-Berechtigungen erhalten. 
- Diese Gruppen können Mitglieder von Standardgruppen sein.
z.B. `\Everyone` und `NT AUTHORITY\Local Account`
## Standardgruppen vs Spezielle Identitätsgruppen
- Benutzer können NUR zu Standardgruppen hinzugefügt werden
- Spezielle Identitätsgruppen sind z. B. Jeder oder Besitzer. Es sind Gruppen die Automatisch von Windows erstellt und verwaltet
- Spezielle Identitätsgruppen können Mitglied von Standardgruppen sein
- Standardgruppen können *nicht* verschachtelt werden

# Benutzerprofile
- Liegen unter `C:\Users\[username]`
- Vorlage für den Userordner ist `C:\Users\Default`
- `NTUSER.DAT` enthält die Registry Einstellungen
## Profil löschen
Profile müssen über Systemeinstellungen -> Benutzerprofile gelöscht werden.
Wenn man nur den Ordner löscht bleiben die Registry Werte bestehen

# Benutzerrechte
- Systemprivilegien sind im Access-Token gespeichert (wird beim anmelden erstellt) 
- *WICHTIG*: Anzeigen der aktuellen Privilegien`whoami /priv`
- Privilegien ändern mit MMC in Gruppenrichtlinien