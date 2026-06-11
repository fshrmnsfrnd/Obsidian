---
Fach: "[[BA]]"
tags:
Thema:
  - "[[Linux]]"
---
>In einer swap Partition oder Datei kann der RAM Daten auslagern
# Überprüfen
---
`free -h` zeigt RAM und swap Informationen an.
**Beispiel Output:**
```bash
               total        used        free      shared  buff/cache   available
Mem:           7.4Gi       521Mi       6.8Gi       3.4Mi       305Mi       6.9Gi
Swap:          2.0Gi          0B       2.0Gi
```

`swapon --show`  genauere Informationen zum swap Speicher an
**Beispiel Output:**
```bash
NAME     TYPE      SIZE USED PRIO
/dev/sdc partition   2G   0B   -2
```
# SWAP Datei verwalten
---
`sudo dphys-swapfile swapoff` schaltet die swap Datei ab.
`sudo dphys-swapfile swapon` schaltet die swap Datei an.

`sudo systemctl disable dphys-swapfile` deaktiviert den Autostart der Datei

`sudo dphys-swapfile uninstall` entfernt das swap File
# SWAP Partition verwalten
---
Die Partition muss als `linux-swap` partitioniert sein.

`sudo swapoff /dev/sda1` deaktiviert die swap-Partition.
`sudo swapon /dev/sda1` aktiviert die swap-Partition.
## swap in der fstab
`/dev/sda1   none   swap   sw   0   0`