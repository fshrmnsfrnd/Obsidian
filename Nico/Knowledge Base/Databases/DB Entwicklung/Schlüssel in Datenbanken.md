---
Thema:
  - "[[Databases]]"
---
>Definition Schlüssel: Ein Schlüssel ist eine minimale Menge von Attributen, deren Werte den zugeordneten Datensatz eindeutig identifizieren

>Schlüssel werden in der eigenen Tabelle als Primary Key / Primärschlüssel verwendet

# Schlüsselarten
---
![[Pasted image 20241106011437.png]]
## Superschlüssel
Menge von Attributen, die die Möglichkeit bieten, einen Datensatz eindeutig zu identifizieren
## Schlüsselkandidat
Eine **minimale** Teilmenge der Attribute eines Superschlüssels.
Es kann mehrere Schlüsselkandidaten geben.
## Künstlicher Schlüssel / Ersatzschlüssel
Dies ist ein hinzugefügtes Attribut, das nicht aus Daten der Tabelle abgeleitet ist, sondern von außen generiert wurde.
Beispiele:
- Laufende Nummern (1, 2, 3, 4, ...)
- UUID/GUID (generierte 16 Byte Zahl)
# Fremdschlüssel / Foreign Key
---
Diese werden verwendet um Datensätze zu verbinden.
Das sind immer Primary Keys von anderen Tabellen.