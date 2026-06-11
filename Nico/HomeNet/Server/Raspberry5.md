# Docker
---
[[Knowledge Base/Tools/Docker]]
Alle Server laufen in Dockern
# Immich
---
[[Immich]]
`docker-compose.yml`, `.env` und `ImmichLibrary` liegen unter `docker/Immich/`

Erreichbar unter:
raspberry5:2283
immich.fshrmnsfrnd.ddnss.de:443

# NGINX Proxy
---
[[NGINX]]
`docker-compose.yml` liegt unter `/docker/ReverseProxy/`

Erreichbar unter:
Admin Panel: `http://raspberry4:81/login`

# Portainer
---
[[Portainer]]
Erreichbar unter: 
`raspberry5:9443`

Business Licence: 
`3-R3S3AOJc/mfRmwMw02X6yqDX8nBhL20+PCYDbzZcgFX3Uwyd4/kxTrqhjw7Qszo/ghUv4vWTUQ7ktxLIhxDJU4j2afXR5KFcCu+gA9ZLyiLRQR6kK0m+Xi/G/7vyG8k=`

# Rezepte
---
`/docker/Rezepte`
# Cocktails
---
`/docker/Cocktails`
# Quartz
---
`/docker/Quartz`
# Backup
---
Das Backup von `/docker/Nextcloud/NextcloudStorage` und `/docker/Immich/ImmichLibrary` wird mit [[Restic]] nach `/mnt/backup` gemacht. Das Passwort ist im Passwort File

`/mnt/backup` ist eine `smb` Freigabe vom [[Raspberry3]] eingebunden über die fstab
**fstab:**
```
//192.168.178.26/backup /mnt/backup cifs uid=nico,gid=nico,username=nico,password=<password>,iocharset=utf8,file_mode=0700,dir_mode=0700
```

**Password file:** `/mnt/backup/resticpwd`

Automatisiert mit Cron:
**Immich Database Dump**
`30   3  * * *   root    /usr/bin/docker exec -t immich_postgres pg_dumpall --clean --if-exists --username=postgres | gzip > "/docker/Immich/ImmichLibrary/dump.sql.gz"`

**Nextcloud Data Backup**
`0 3 * * * root /usr/bin/restic -r /mnt/backup/NextcloudStorage_Backup backup /docker/Nextcloud/nextcloudStorage --password-file /mnt/backup/resticpwd >> /mnt/backup/restic-backup.log 2>&1`

**Immich Data Backup**
`0 4 * * * root /usr/bin/restic -r /mnt/backup/ImmichLibrary_Backup backup /docker/Immich/ImmichLibrary --password-file /mnt/backup/resticpwd >> /mnt/backup/restic-backup.log 2>&1`

Die Logs vom Backup werden in `/mnt/backup/restic-backup.log` geschrieben