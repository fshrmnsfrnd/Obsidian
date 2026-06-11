---
Thema:
  - "[[HomeLab]]"
---
https://github.com/restic/

>Backup Tool, das nur Client Side läuft, Server Side ist nur ein freigegebener Speicherort nötig

# Initialisieren
`restic init --repo </path/to/restic/repository> --password-file /path/to/pwdfile`

Auf dem System, dass gesichert werden soll muss dieser Command ausgeführt werden. Der Pfad ist der Pfad wo das Backup liegen wird.

# Backup erstellen
`restic -r </path/to/restic/repository> [--verbose=2] backup </path/to/source/directory> --password-file /path/to/pwdfile` 

Dieser Command erstellt ein Backup von `/path/to/source/directory` in `</path/to/restic/repository>` 
Ist bereits ein Backup vorhanden, wird es inkrementell fortgeführt.

# Backups anzeigen
`restic snapshots -r </path/to/restic/repository> --password-file </path/to/pwdfile>`

Zeigt die erstellten Backups in `</path/to/restic/repository>` mit Datum/Uhrzeit an.
# Wiederherstellen
`restic restore -r </path/to/restic/repository> <backupID> --target </path/to/target/directory>` `

Der Stand des Directorys von `<backupID>` wird in `/path/to/target/directory` wiederhergestellt.

> [!NOTE] Best Practise für Wiederherstellen
> Die Daten aus dem Target Directory werden werden nicht entfernt. Das heißt nach dem wiederherstellen hätte man beide Versionen nebeneinander im Directory legen. 
> **Besser:**
> Als Target Directory ein temporäres Directory verwenden, dann das eigentliche Directory leeren und die Daten aus dem temporären Directory in das eigentliche Directory kopieren

