---
Fach:
Thema:
  - "[[Security]]"
---
>Die **Cross-Zertifizierung** ermöglicht die **gegenseitige Anerkennung von Zertifikaten** zwischen verschiedenen hierarchischen PKIs.  
>Dabei stellen sich zwei **Zertifizierungsstellen (meist Root-CAs)** gegenseitig **Cross-[[Zertifikate]]** aus.

![[Pasted image 20251117235002.png]]
# Merkmale
---
- Ausdruck des **gegenseitigen Vertrauens zweier gleichberechtigter PKIs**.  
- Keine der beiden Parteien ist der anderen übergeordnet.  
- Die **Regelwerke** einer PKI gelten für die andere nur, **sofern sie nicht im Widerspruch** zu deren eigenen Regeln stehen.  
- Die **Interpretation der Vertrauensbeziehung** ist oft komplex oder uneindeutig.
# Problem der Skalierung
---
- Bei **bilateraler Cross-Zertifizierung** steigt die Zahl der Cross-[[Zertifikate]] **quadratisch** mit der Anzahl der Stammzertifizierungsstellen.  
  Beispiel:  
  - 20 Stamminstanzen ⇒ 20 × 19 = **380 Cross-[[Zertifikate]]** erforderlich.
# Lösung: Bridge-CA
---
- Eine **Bridge-CA** dient als **neutrale Vermittlungsinstanz**.  
- Jede beteiligte Root-CA tauscht **nur ein Cross-Zertifikat** mit der Bridge-CA aus.  
- Dadurch lassen sich [[Zertifikate]] **über die Bridge-CA auf alle anderen PKIs** zurückführen.  
- Dieses Modell wird auch als **„Hub and Spoke“** bezeichnet:  
  - **Hub:** Bridge-CA als zentraler Knotenpunkt.  
  - **Spokes:** die einzelnen verbundenen PKIs.
![[Pasted image 20251111165617.png]]

**Ergebnis:**  
Die Cross-Zertifizierung schafft **Vertrauen zwischen unabhängigen PKIs**, entweder **direkt bilateral** oder **zentral über eine Bridge-CA**, wodurch eine **interoperable Vertrauensinfrastruktur** entsteht.