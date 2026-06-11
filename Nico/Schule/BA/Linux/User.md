---
Fach: "[[BA]]"
Thema:
  - "[[Linux]]"
---
# /etc/passwd
---
`Username : Passwort : UserID : GroupID : Beschreibung : Homeverzeichnis : Startshell` 
- Username: Anmeldename
- Passwort: x ⇒ Passwort in /etc/shadow
- UserID: 0-65535, root hat immer 0
- GroupID: ID der primären Gruppe des Users (0-65535)
- Beschreibung: z.B. Vorname, Nachname, …
- Homeverzeichnis: Startverzeichnis
- Startshell: Programm, das nach der Anmeldung ausgeführt wird
# /etc/shadow
---
`Username : Passwort : DOC : MinD : MaxD: Warn : Exp : Dis: Reserviert`
- Username: Anmeldename
- Passwort: * → User kann sich nicht anmelden
- DOC: Day of last change (Tage seit 1.1.1970)
- MinD: Anzahl der Tage, nachdem Passwort geändert werden darf
- MaxD: Anzahl der Tage, bis wann ein Passwort geändert werden muß
- Warn: Anzahl der Tage vor dem Ablaufen des Passworts, ab denen User Warnung erhält
- Exp: Anzahl der Tage nach dem Auslaufen des Passworts, bis der Account tatsächlich ungültig wird.
- Dis: Anzahl der Tage vom 1.1.1970 bis zu dem Tag, an dem das Passwort ungültig wird (festes Datum als Ergänzung zu den anderen Einstellungen)
- Reserviert: für zukünftige Erweiterungen
# /etc/group
---
`Gruppenname : Passwort : GroupID : Mitgliederliste`
- Gruppenname: Name der Gruppe
- Passwort: x → Passwort in /etc/gshadow
- GroupID: 0-65535, root hat immer 0
- Mitgliederliste: durch Kommas getrennte Liste von Usernamen 
# /etc/gshadow
---
`Gruppenname : Passwort : Gruppenverwalter : Mitgliederliste`
- Gruppenname: Name der Gruppe
- Passwort: * oder ! ⇒ kein Passwort. Das Passwort wird benötigt, um mit dem Befehl newgrp vorrübergehend Rechte der Gruppe zu erhalten.
- Gruppenverwalter: UID des Gruppenverwalters, der andere Mitglieder aufnehmen und entfernen und das Gruppenpasswort ändern kann
- Mitgliederliste: durch Kommas getrennte Liste von Usernamen
