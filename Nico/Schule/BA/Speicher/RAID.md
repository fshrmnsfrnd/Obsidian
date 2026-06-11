---
Fach: "[[BA]]"
tags:
---
# RAID 0 (Stripeset)
---
- mindestens zwei Festplatten 
- keine Redundanz 
- evtl. Geschwindigkeitsvorteil

![[Pasted image 20250601142853.png]]

Speicherplatz = Summe des Speichers aller Festplatten
# RAID 1 (Mirror)
---
- mindestens zwei Festplatten 
- Redundanz

![[Pasted image 20250601142941.png]]

Speicherplatz = Speicherplatz der kleinsten Festplatte
# RAID 2
---
Bit-Level Striping mit Hamming-Code-basierter Fehlerkorrektur
Veraltet
# RAID 3 (Parity Disk)
---
Wie RAID 5 nur dass die Parities alle auf der selben Platte liegen.
Veraltet
# RAID 4
---
Ähnlich wie RAID 5 aber veraltet
# RAID 5 (Cycling Parity)
---
- mindestens drei Festplatten
- Redundanz 
- evtl. Geschwindigkeitsvorteil gegenüber RAID 1 (Mirror)

![[Pasted image 20250601143055.png]]

Speicherplatz = Speicherplatz der kleinsten Platte mal 2
# RAID 6 (Double Cycling Parity)
---
- Mindestanzahl Festplatten: 4
- Redundanz: Zwei Paritätsblöcke → Ausfall von bis zu 2 Platten tolerierbar
- Paritätsverteilung: doppelte Parität (z. B. P und Q), verteilt über alle Platten
- Performance:
    - Lesen: ähnlich wie RAID5 (gut)
    - Schreiben: höherer Overhead als RAID5 (schlechter)
- Speicherplatz (bei gleichen Plattenkapazitäten): (N - 2) × Größe_der_kleinsten_Platte
- Einsatz: große Arrays mit höherer Ausfallsicherheit als RAID5
# Geläufige RAID‑Kombinationen
---
- Ziel: Redundanz + Performance durch Kombination von Mirroring und Striping oder Parity-Gruppen.
- Min‑Disks, nutzbare Kapazität und Ausfallsicherheit hängen von Aufbau (Gruppengröße) ab.

| Name                                         | Min. Platten    | Usable-Kapazität (bei gleichen Platten)    | Ausfallsicherheit (typ.)                                    | Vor-/Nachteile                                                                                                                |
| -------------------------------------------- | --------------- | ------------------------------------------ | ----------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| RAID 10 (Striped Mirrors)                    | 4               | N/2 × Größe                                | pro Mirror‑Pair 1 Platte (mehrere möglich, abhängig Lage)   | sehr gute Lese-/Schreibleistung, hohe Ausfallsicherheit; teuer (50% Overhead)                                                 |
| RAID 01 (Mirrored Stripe)                    | 4               | N/2 × Größe                                | bei Ausfall in einem Stripe ggf. kompletter Stripe verloren | ähnlich Leistung wie 10, schlechtere Fehlertoleranz als RAID10                                                                |
| RAID 50 (Striping über RAID5-Gruppen)        | 6 (mind. 2 x 3) | (Gesamtplatten − Anzahl_Gruppen) × Größe   | pro RAID5‑Gruppe 1 Platte                                   | bessere Schreib-/Leseleistung als einzelnes RAID5, höhere Kapazitätseffizienz; komplexer, Paritätsrekonstruktion gruppenweise |
| RAID 60 (Striping über RAID6-Gruppen)        | 8 (mind. 2 x 4) | (Gesamtplatten − 2×Anzahl_Gruppen) × Größe | pro RAID6‑Gruppe 2 Platten                                  | sehr hohe Ausfallsicherheit, geeignet für große Arrays; hoher Overhead/Komplexität                                            |
| RAID 1E (Striped Mirror für ungerade Anzahl) | 3               | ca. floor(N/2) × Größe                     | ähnlich RAID1 je nach Paarung                               | Mirror‑Vorteile bei ungerader Plattenzahl; weniger geläufig                                                                   |
| JBOD / Concatenation                         | 1               | Summe aller Platten                        | keine                                                       | einfach, keine Redundanz; nur Kapazitätserweiterung                                                                           |

Beispiel‑Kapazitätsberechnung (alle Platten gleich groß S):
- RAID6 mit N Platten: nutzbar = (N − 2) × S  
- RAID10 mit N (gerade) Platten: nutzbar = N/2 × S  
- RAID50 mit k Gruppen à g Platten (je Gruppe RAID5): nutzbar = (k × (g − 1)) × S