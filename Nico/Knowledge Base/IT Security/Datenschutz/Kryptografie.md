---
Thema:
  - "[[Security]]"
---
Kryptografie dient zur geheimen Kommunikation gegen unbefugte Entschlüsselung und die Informationsgewinnung aus verschlüsselten fremden Nachrichten. Dadurch sollen also Daten sicher versendet und Empfangen werden. Kryptografie schützt die Schutzziele:  
**- Vertraulichkeit**  
**- Integrität**  
**- Authentizität**

# Verschlüsselungsverfahren
---
**Verschlüsselungsverfahren schützen NUR die Vertraulichkeit!**
## Symmetrisch
![[1IqXX05xzz-700.webp]]

| **Vorteile**                       | **Nachteile**               |
| ---------------------------------- | --------------------------- |
| schnell                            | Schlüssel austausch Problem |
| sicherer nach Schlüsselübertragung |                             |
**Verfahren:** AES, DES, 3DES
## Asymmetrisch
![[X8iUGHTLj_-700.webp]]

|**Vorteile**|**Nachteile**|
|---|---|
|kein schlüssel austausch Problem|langsam (1000 - 10000 mal)|
||Angreifer versuche aus Public Key den Private Key zu berechnen|
**Verfahren:** RSA, Elgamal-Kryptosystem
## Hybrid
![[z9I_jeVoDA-700.webp]]

|**Vorteile**|**Nachteile**|
|---|---|
|Schnell|aufwendig|
|keine austausch Problem||
|**Verfahren:** SSH, HTTPS, SSL/TLS||
# Digitale Signatur
 ![[K_NOWietfL-700.webp]]
**Digitale Signatur schützt NUR die Integrität und Authentizität!**
# Digitale Signatur kombiniert mit Verschlüsselung
![[1K8lRucysQ-700.webp]]