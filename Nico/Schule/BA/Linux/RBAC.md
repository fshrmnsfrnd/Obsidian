---
Thema:
  - "[[Linux]]"
---
>**R**ole **B**ased **A**ccess **C**ontrol
>Zugriffsberechtigungen auf Ressourcen werden nicht an einzelne Benutzerkonten, sondern an Rollen (Gruppen) vergeben, die den Benutzerkonten zugewiesen werden.

> [!WARNING] Mit "normalen" Linux Berechtigungen nicht möglich
> Linux kann per default nur eine Gruppe pro Ressource zulassen, es werden aber mehrere benötigt. Dafür gibt es z.B. `getfacl` bzw. `setfacl`
> Außerdem können Gruppen nicht verschachtelt werden
# Umsetzung mit normalen Linux Berechtigungen
---
## 1. Verzeichnisstruktur aufsetzen

| Verzeichnis                  | user | userrechte | group          | grouprechte | others |
| ---------------------------- | ---- | ---------- | -------------- | ----------- | ------ |
| verzeichnis-oben             | root | `rwx`      | verzeichnis-r  | `r-x`       | `---`  |
| verzeichnis-oben/verzeichnis | root | `rwx`      | verzeichnis-rw | `rwx`       | `r-x`  |
## 2. Benutzer den Gruppen zuordnen
---

| Gruppe         | Mitglieder                     |
| -------------- | ------------------------------ |
| verzeichnis-r  | Alle mit `R` oder `RW` Rechten |
| verzeichnis-rw | Nur die mit `RW` Rechten       |
# Beispiel
---
- Lara und Luis sind Lehrer
- Sarah und Sepp sind Schüler
- Petra ist Praktikantin
- Lehrer dürfen in Vorlagen und in Austausch lesen und schreiben
- Schüler dürfen Vorlagen lesen und Austausch schreiben
- Praktikanten dürfen nichts

| Gruppe       | Mitglieder              |
| ------------ | ----------------------- |
| Austausch-R  | Lara, Luis, Sarah, Sepp |
| Austausch-RW | Lara, Luis, Sarah, Sepp |
| Vorlagen-R   | Lara, Luis, Sarah, Sepp |
| Vorlagen-RW  | Lara, Luis              |

| Verzeichnis              | user | userrechte | group        | grouprechte | others |
| ------------------------ | ---- | ---------- | ------------ | ----------- | ------ |
| Austausch-oben           | root | `rwx`      | Austausch-R  | `r-x`       | `---`  |
| Austausch-oben/Austausch | root | `rwx`      | Austausch-RW | `rwx`       | `r-x`  |
| Vorlagen-oben            | root | `rwx`      | Vorlagen-R   | `r-x`       | `---`  |
| Vorlagen-oben/Vorlagen   | root | `rwx`      | Vorlagen-RW  | `rwx`       | `r-x`  |