---
Fach: "[[BA]]"
tags:
Thema:
  - "[[Operating System]]"
---
# Vergleich Dateisysteme
| Eigenschaft            | FAT (FAT16) | FAT32 | exFAT  | NTFS    | ReFS    |
| ---------------------- | ----------- | ----- | ------ | ------- | ------- |
| max. Dateigröße        | 4 GiB       | 4 GiB | 512 TB | 16 TiB  | 35 PB   |
| max. Größe des Volumes | 4 GiB       | 2 TiB | 512 TB | 256 TiB | 4 ZiB   |
| Zugriffsberechtigungen | -           | -     | -      | Windows | Windows |
# Windows Standard Dateiattribute
- schreibgeschützt 
- versteckt 
- Archiv 
- System

## Zusätzliche NTFS-Attribute
- Komprimierung von Ordnern 
- Verschlüsselung einzelner Ordner und Dateien 
- EFS (Encrypting Filesystem) 
- Die Ordner und Dateien können nur vom jeweiligen Benutzer entschlüsselt werden.
- Eigenschaften des Ordners → Erweiterte Attribute → Inhalt verschlüsseln, um Daten zu schützen 
- mmc-Snap-In: [[Zertifikate]] → Eigene [[Zertifikate]]

# Bitlocker
- Verschlüsselt die gesamte Partition

