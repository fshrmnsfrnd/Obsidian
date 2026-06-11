---
Fach: "[[BA]]"
Thema:
  - "[[Security]]"
---
Gehört zu [[Authentifikation#Besitz]]

Der Nutzer muss aus einer vom Server geschickten Challenge (C) mit Hilfe eines Sicherheitsmoduls eine Response berechnen und zurücksenden. 
![[Pasted image 20260114151107.png]]
Es gibt unterschiedlichen Möglichkeiten das Challenge Response Verfahren umzusetzen: 
1. Berechnung mit einer Hashfunktion und einem Geheimnis (Beide Seiten kennen Hashfunktion und Geheimnis) 
2. Berechnung mit Hilfe eines symmetrischen Verschlüsselungsverfahrens z.B: AES (Beide Seiten kennen den Schlüssel) 
3. Asymetrische Verschlüsselung: Der Nutzer verschlüsselt die Challenge mit Hilfe des privaten Schlüssels. Das IT-System entschlüsselt mit dem öffentlichen Schlüssel (Voraussetzung [[Public Key Infrastruktur (PKI)]] ) 

Wenn das verwendete Hardware Sicherheitsmodul mit einer PIN aktiviert werden muss spricht man von Zweifaktor Authentifizierung (PIN= Wissen, Card = Besitz) = [[Passkeys]] 