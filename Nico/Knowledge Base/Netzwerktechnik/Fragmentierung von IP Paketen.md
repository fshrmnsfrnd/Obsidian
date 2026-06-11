---
Fach:
Thema:
  - "[[Networks]]"
---

> [!NOTE] Hier wird beschrieben wie Frames aus einem Token Ring Netz in ein Ethernet Netz übersetzt werden

>MTU: **M**aximum **T**ransfer **U**nit

- Paket im Token Ring: 4464 Bytes MTU
- Paket im 802.3 (Ethernet): 1492 Bytes MTU
- Beim Übergang von Tokenring zu Ethernet muss das Paket **fragmentiert** werden, weil es zu groß ist
- Fragmente können in unterschiedlicher Reihenfolge im Ethernet Netz beim Host ankommen
	- Daher bekommt das Paket im Ethernet Netz einen SNAP Rahmen
# Fragmentierung
---
![[Fragmentierung von IP Paketen 2026-04-23 12.08.54.excalidraw]]

