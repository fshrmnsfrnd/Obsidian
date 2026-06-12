---
Fach:
Thema:
  - "[[Security]]"
---
# Einfache Verschlüsselung
---
- Fester Algorithmus
- Beispiel: Cäsar Verschlüsselung
# Schlüsselabhängige Verschlüsselung
---
- Verschlüsselung und Entschlüsselung mit einem Schlüssel
- Algorithmus kann unterschiedliche Schlüssel nutzen
- Je länger der Schlüssel desto länger dauert es einen Schlüssel random rauszufinden
# Symmetrische Verschlüsselung
---
- Verschlüsseln und entschlüsseln mit selben Schlüssel
- Beispiel: AES


![[Pasted image 20251118000059.png]]
# Asymmetrische Verschlüsselung
---
Hier ein Schlüssel zum verschlüsseln und ein anderer Schlüssel zum entschlüsseln verwendet. Dafür muss sich jeder Kommunikationspartner ein Schlüsselpaar, bestehend aus Privaten- und Öffentlichen-Schlüssel generieren. 
Der Öffentliche Schlüssel kann verbreitet werden, da dieser nur für das **verschlüsseln** verwendet wird. 
Für das Entschlüsseln wird dann der **geheime** Private-Schlüssel verwendet.
![[Pasted image 20251117235605.png]]
Langsam (rechenintensiv) aber sehr sicher da es das Schlüsselaustauschproblem nicht gibt.
# Hash Funktionen
---
## Eigenschaften
- Der Algorithmus für die Hash-Prüfsummenbildung ist allgemein bekannt. 
- Der Hashwert kann nicht „entschlüsselt“ werden. 
- Es können Hash-Werte aus Daten beliebiger Länge ermittelt werden. 
- Die Wahrscheinlichkeit, dass unterschiedliche Daten zum gleichen Hash-Wert führen, muss sehr gering sein. Es ist auch keine systematische Erzeugung einer bestimmten Prüfsumme möglich. (Kollisionsresistenz)

## Beispiele
- SHA1,SHA2, SHA-3, SHA256
- MD5 128Bit Hash (nicht sicher, nicht kollisionsresistent) 
- PBKDF2 (Password Based Key Derivation Function 2) , komplizierter Algorithmus für Passwörter
- Bcrypt und Scyrpt , Passwort Hash Algorithmen basierend auf Blowfish