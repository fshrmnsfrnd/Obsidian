# Docker
[[Knowledge Base/Tools/Docker]]
# Speicher
```bash
lsblk:
NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
sda           8:0    0 238.5G  0 disk
├─sda1        8:1    0     4G  0 part [SWAP]
└─sda2        8:2    0 234.5G  0 part /mnt/NextcloudStorage
sdb           8:16   0 238.5G  0 disk
└─sdb1        8:17   0 238.5G  0 part /mnt/ImmichLibrary
mmcblk0     179:0    0 119.1G  0 disk
├─mmcblk0p1 179:1    0   256M  0 part /boot
└─mmcblk0p2 179:2    0 118.8G  0 part /
```

# Lüfter
---
Dass der Lüfter schon bei 45 Grad angeht, gibt es einen Eintrag in `/boot/firmware/config.txt` 
`raspi-config` gibt einen minimalwert von 60 Grad vor