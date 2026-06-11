---
Fach: "[[BA]]"
Thema:
  - "[[Security]]"
---
# Passkeys vs Passwords
---
- Passkeys können nicht zu simpel oder zu kurz sein – Passwörter dagegen schon.
- Passkeys können im Gegensatz zu Passwörtern nicht vergessen werden.
- Passkeys werden schnell und automatisiert erstellt.
- Es ist unwahrscheinlicher, dass Passkeys durch Phishing oder Datendiebstahl verloren gehen.
- Jeder Passkey schützt immer genau einen Account – so können nie mehrere Accounts gefährdet sein, sollte ein Passkey missbraucht werden.

# Was ist ein Passkey
---
Wenn ein Passkey erstellt wird, werden zwei kryptografische Schlüssel generiert:
1. **Public Key**: Dieser bleibt auf dem Server des Dienstanbieters. Er ist für sich genommen nicht sensibel und kann nicht für den Zugriff auf Ihr Konto verwendet werden.
2. **Private Key**: Dieser befindet sich auf dem Gerät des Benutzers, z. B. einem Smartphone. Er verlässt das Gerät nie und ist immer durch eine starke Form der Benutzerverifizierung geschützt(Face ID o.ä.).

## Funktionsweise
---
Der Public Key wird auf den Servern des Dienstes gespeichert, während der private Key sicher auf Ihrem Gerät gespeichert ist. 
Und zwar in speziellen Komponenten wie Secure Enclave auf Apple Geräten, Trusted Platform Module (TPM) auf Windows und Android und Samsung Knox für Galaxy Geräte. 
Diese Komponenten sind vom Hauptprozessor isoliert und dienen als Tresor, in dem selbst im Falle eines Malware Angriffs oder einer Sicherheitsverletzung die sensiblen Benutzerdaten sicher bleiben.

**Passkeys funktionieren auch über verschiedene Geräte**. Dank sicherer Ökosysteme werden die privaten Keys über alle Geräte hinweg synchronisiert, so dass die Authentifizierung auf jedem Gerät, auf dem ein Cloud Konto wie iCloud oder Google aktiv ist, einwandfrei funktioniert.
![[5465660151668270524_1024x1024.webp]]
## Ablauf
1) **Du** besitzt den **Private Key**  
2) Der **Anbieter** den **Public Key**  
3) Du clickst "Mit Passkey anmelden"  
4) Anbieter erstellt eine **Challenge** Er erstellt zufällige Daten, welche nur für diese Anmeldung gültig sind und schickt sie an dein Gerät  
5) Du **signierst diese Daten** mit deinem **Privaten Schlüssel** und schickst sie zurück  
6) Anbieter **überprüft** diese Signatur dann mit dem Public Key
# Verwendung
---
Bei der Anmeldung bittet der Dienst den Benutzer nicht um ein Passwort. Es verwendet ein Entsperrmechanismus des Geräts.

Das Gerät signiert die Herausforderung mit dem privaten Key und sendet sie über den öffentlichen Key an den Dienst zurück, damit sie überprüft wird. Der private Key ist auf eine bestimmte Domäne beschränkt.

Das Gerät erstellt für jeden Anmeldeversuch eine zeitbasierte Signatur, die kurz nach ihrer Erstellung abläuft. So wird dafür gesorgt, dass sie, selbst wenn sie abgefangen wird, nicht wiederverwendet oder ausgenutzt werden kann.

Dies geschieht direkt und sofort, und bietet eine sehr sichere und einfache Anmeldung.