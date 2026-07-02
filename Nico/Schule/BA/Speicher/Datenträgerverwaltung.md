---
tags:
Fach: "[[BA]]"
Thema:
  - "[[Operating System]]"
  - "[[Storage]]"
---
> [!Warning] Volume ≠ Partition
> **Partition:** Physischer aufeinanderfolgender Bereich von Sektoren
> **Volume:** Logischer Bereich eines Dateisystems
# Windows
---
- Datenträgerverwaltung (GUI)
- Powershell
	- Get-Disk
	- Get-Partition
- diskpart (CMD)
	- list disk
	- select disk >Number<
	- detail disk
# Linux
---
- gParted (GUI)
- parted (Terminal)
- lsblk (informationen über angeschlossene Platten)
- blkid (IDs, Labels usw. angeschlossener Platten) 
# Partitionstabelle
---
## MBR (Master Boot Record)
- max 4 Partitionen
- max 4TiB Festplatte
- max 2TiB Partition
- kann kein UEFI
## GPT (GUID Partition Table)
- max 128 Partitionen
- Kann UEFI
- Max Größe fast unbegrenzt
# Speicher unter Linux
---
Jede Festplatte oder Partition hat in `/dev/` eine Datei
```
/dev/sda1
/dev/sda2
...
/dev/sdb1
/dev/sdb2
```
`SD` : Solid Disk, beschreibt dass es eine Festplattendatei ist
Buchstabe: Jede Physische Platte bekommt einen Buchstaben
Zahl: Jede Partition auf einer Platte bekommt eine Zahl

In der `/etc/fstab` Datei ist beschrieben welche Datei beim Start des Systems wo eingehangen werden soll

