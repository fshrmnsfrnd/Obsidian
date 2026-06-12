---
Fach:
Thema:
  - "[[Security]]"
---
Zur Erhöhung der Sicherheit kann bei der Authentifizierung auf die Kombination mehrerer Authentifikationsverfahren zurückgegriffen werden. 
- Man spricht von einer 2 Faktor Authentifizierung, wenn 2 Faktoren verwendet werden. Beispiel: Hardware-Sicherheitsmodul (Besitz) und PIN (Wissen) bei Bankkarten. 
- Bei einer Multifaktor Authentifizierung wird eine Kombination von zwei oder mehr unterschiedlichen Faktoren genutzt. 
  Beispiel: Challenge Response mithilfe eines [[Hardware Sicherheitsmodule (HSM)]] (Besitz) mit PIN (Wissen) plus Fingerabdruck (Sein) (Smartphone) 

Für die Multifaktor-Authentifikation sind neben Hardware-Sicherheitsmodulen auch Authentifizierungsmanager notwendig die die Identifikation und die Authentifizierung des Nutzers übernehmen. Der Dienstanbieter kommuniziert für die Authentifikation mit dem Authentifizierungsmanager.

# Beispiel: FIDO2 Authentifikation
![[Pasted image 20260114153815.png]]
