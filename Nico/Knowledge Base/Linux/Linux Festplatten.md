---
Thema:
  - "[[Operating System]]"
  - "[[Linux]]"
---
# Disk Infos
---
## blkid
```Shell
/dev/xxx: LABEL_FATBOOT="bootfs" LABEL="bootfs" UUID="XXX-XXX" BLOCK_SIZE="512" TYPE="vfat" PARTUUID="xxx"
```
## lsblk
```Shell
NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
sdb           8:16   0 931.5G  0 disk 
├─sdb1        8:17   0     4G  0 part 
└─sdb2        8:18   0 781.3G  0 part 
```
## df -T
```Shell
Filesystem     Type     1K-blocks     Used Available Use% Mounted on
/dev/mmcblk0p1 vfat        522230    60264    461966  12% /boot/firmware
/dev/sda2      btrfs    819200000 70535284 746804556   9% /mnt/Backup
tmpfs          tmpfs        92788        0     92788   0% /run/user/1000
```
## df -h
```shell
Filesystem  Size  Used Avail Use% Mounted on
mmcblk0p2   117G  2.8G  109G   3% /
/dev/sda2   782G   68G  713G   9% /mnt/Backup
tmpfs        91M     0   91M   0% /run/user/1000
```
# btrfs
---
## relabel
```shell
# If not mountet
btrfs filesystem label /dev/sdx [newlabel]
# If mounted
btrfs filesystem label /mountpath [newlabel]
```
# Mount
---
## Mount everything from fstab
```shell
mount -a
```

