---
Fach:
Thema:
  - "[[Security]]"
---

>Das **Web of Trust** ist ein alternatives Vertrauensmodell zu klassischen hierarchischen PKIs.  
>Es wird von Verschlüsselungsprogrammen wie **PGP** und dessen Open-Source-Variante **GNU Privacy Guard (GPG)** genutzt, basierend auf **OpenPGP**.
# Funktionsweise
- **Jeder Benutzer** kann selbst [[Zertifikate]] erstellen.  
- Wenn ein Benutzer einem öffentlichen Schlüssel vertraut und glaubt, dass er zur angegebenen Person gehört, **signiert er diesen Schlüssel**.  
- Andere Benutzer können anhand der [[Signaturen]] entscheiden, ob sie dem Schlüssel ebenfalls vertrauen wollen.  
- **Je mehr [[Signaturen]] ([[Zertifikate]]) ein Schlüssel hat, desto höher das Vertrauen in dessen Echtheit.**
# Besonderheiten
- Ein Zertifikat kann auch von einer **Zertifizierungsstelle (CA)** im Web of Trust ausgestellt werden.  
- In diesem Fall entsteht ein **teilweise hierarchisches Modell**, da die CA Regeln für die Zertifikatsausstellung vorgibt.  
# Beispiele für PKI-Strukturen
- **TLS/SSL** (typisch hierarchisch, für Webanwendungen)  
- **E-Mail-Verschlüsselung** mit **PGP / OpenPGP** (Web of Trust)  
