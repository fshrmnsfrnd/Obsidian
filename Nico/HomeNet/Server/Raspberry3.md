# PiHole
[[PiHole]]

PiHole wird benötigt um die Domain fshrmnsfrnd.ddnss.de richtig aufzulösen.
In PiHole ist für diese Domain der [[Raspberry5]] hinterlegt. Wäre das nicht so, würde die [[FritzBox]] die Domain auf sich selbst auflösen

Erreichbar unter:
`raspberry3:80` 

# Speicher
```bash
lsblk:
NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
sda           8:0    0 931.5G  0 disk
├─sda1        8:1    0     4G  0 part [SWAP]
└─sda2        8:2    0 781.3G  0 part /mnt/Backup
mmcblk0     179:0    0 119.1G  0 disk
├─mmcblk0p1 179:1    0   512M  0 part /boot/firmware
└─mmcblk0p2 179:2    0 118.6G  0 part /`
```
>**Achtung:** auf der `SDA` ist noch Speicher frei

# SMB Share
[[Samba]]
**fstab:** 
`/dev/sda2               /mnt/Backup     btrfs   defaults                0       2`
