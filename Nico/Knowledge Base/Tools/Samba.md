---
Thema:
  - "[[Linux]]"
---
>**Samba** ist die führende Open-Source-Implementierung des **SMB**-Protokolls (Server Message Block) für Linux- und Unix-Systeme.  Während **SMB** (in moderneren Versionen oft als **CIFS** bezeichnet) das von Microsoft entwickelte Netzwerkprotokoll für Dateifreigaben, Drucker und Authentifizierung ist, stellt Samba die Software bereit, um diese Dienste unter nicht-Windows-Betriebssystemen verfügbar zu machen.
# Konfiguration
---
Die Samba Konfiguration liegt in `/etc/samba/smb.conf`
```
[<Name des Shares>]
        comment = Kommentar
        browseable = [yes|no]
        read only = [yes|no]
        guest ok = [yes|no]
        path = /pfad/zur/freigabe
        create mask = 0700
        directory mask = 0700
        valid users = user1
        write list = user1

```
# Passwort für Samba User
---
 Passwort ändern
 `sudo smbpasswd -a <username>`
# Server neu starten
---
`sudo systemctl restart smbd`
# Auf Client einbinden
---
**fstab:**
```
//<servername/ip>/freigebaNameAussmb.conf </pfad/zum/mount/ziel> cifs uid=<user>,gid=<group>,username=<smbUserName>,password=<smbPassword>,iocharset=utf8,file_mode=0700,dir_mode=0700
```
