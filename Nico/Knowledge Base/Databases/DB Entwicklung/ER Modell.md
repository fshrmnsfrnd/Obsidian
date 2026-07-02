---
Thema:
  - "[[Databases]]"
  - "[[Relational Databases]]"
---
>Das Entity-Relationship-Modell kurz ER-Modell oder ERM ist Grundlage eines Datenbankentwurfs. 
# Entität (Entity)
---
Eine Entität ist ein eindeutig identifizierbares Objekt.
z.B.
- eine Person
- ein reales Objekt (z.B. ein Raum)
- ein Konzept (z.B. Unterrichtsfach)
# Entitätsmenge (Entity-Set)
---
Eine Entitätsmenge fasst alle Entitäten zusammen, die durch gleiche Eigenschaften, nicht notwendigerweise aber durch gleiche Eigenschafts-Werte, charakterisiert sind. 
z.B. alle Mitglieder eines Sportvereins. Mitglied ist eine Entität und die einzelnen Mitglieder zusammen sind eine Entitätsmenge.
# Entitäts-Typ (Entity Type)
---
ist eine Zusammenfassung gleichartiger Entitäten.
z.B. Das Mitglied Hans-Jürgen hat den Entitätstyp Mitglied
wird als Rechteck dargestellt
![[ER Modell 2024-11-08 17.12.29.excalidraw]]
# Beziehung, Assoziation (Relationship)
---
Bedeutet, eine Entität steht in Verbindung mit einer anderen Entität.
z.B. Das Mitglied Hans-Jürgen **wohnt in** München
# Beziehungsmenge
---
Eine Beziehungsmenge sind alle Beziehungen der gleichen Art, also eine Beziehung zwischen zwei [[ER Modell#Entitätsmenge (Entity-Set)|Entitätsmengen]].
z.B. alle Beziehungen, in denen Mitglied mit der Wohn Adresse verbunden ist.
# Beziehungstyp
---
Der Beziehungstyp fasst Beziehungen gleichen Typs unter einer Bezeichnung zusammen.
Er wird als Raute dargestellt.
![[ER Modell 2024-11-09 13.52.41.excalidraw]]
# Eigenschaften / Attribute
---
Eigenschaften werden als **Ellipse** dargestellt
**Begriffe:**
- Attributs-Name:
	- z.B. Geburtstag
- Attributs-Wert:
	- z.B. 22.11.2003
- Attributs-Domäne:
	- alle theoretisch gültigen Daten(Wertebereich)

>Die Eigenschaft die der [[Schlüssel in Datenbanken|Primary Key]] ist, wird unterstichen

![[ER Modell 2024-11-09 14.00.59.excalidraw]]

