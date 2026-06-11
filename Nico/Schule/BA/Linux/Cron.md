---
Fach: "[[BA]]"
tags:
Thema:
  - "[[Linux]]"
---
>Cron ist ein Zeitbasierter Deamon auf Linux, der Befehle ausführt
>Systemweite Dateien liegen in `/etc/`
>Benutzerbezogene Dateien liegen in `/var/spool/cron/crontabs/`

# Crontab
Crontab ist der Command für die Konsole, mit dem Cronjobs gelesen und bearbeitet werden können
```
crontab [ -u user ] [ -i ] { -e | -l | -r }
         (default operation is replace, per 1003.2)
        -e      (edit user's crontab)
        -l      (list user's crontab)
        -r      (delete user's crontab)
        -i      (prompt before deleting user's crontab)
```

# Zeitsteuerung
```
┌───────────── Minute (0 - 59)
│ ┌───────────── Stunde (0 - 23)
│ │ ┌───────────── Tag des Monats (1 - 31)
│ │ │ ┌───────────── Monat (1 - 12)
│ │ │ │ ┌───────────── Wochentag (0 - 6)
│ │ │ │ │
* * * * *  user /Pfad/Programmname
```
`*` steht für *jede(n)*. 

# Eventsteuerung
auch z.B. `@reboot` ist als Trigger für den Job möglich.