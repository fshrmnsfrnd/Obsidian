---
Fach: "[[ITS]]"
Thema:
  - "[[Security]]"
---
>In einer **hierarchischen PKI** existiert eine **Stammzertifizierungsinstanz (Root-CA)**, der alle Teilnehmer vertrauen.  
Sie bildet den **Vertrauensanker** des Systems.
# Merkmale
---
- **Root-CA** stellt **Stammzertifikate (Root Certificates)** aus.  
- **Unterzertifikate** werden durch nachgeordnete CAs erstellt.  
- Jedes Zertifikat verweist auf das übergeordnete, wodurch eine **Zertifikatskette** entsteht.  
- Diese Kette wird zur Prüfung der **Vertrauenswürdigkeit, Gültigkeit und Sperrung** herangezogen.

# Praktische Umsetzung
---
- Es existiert **keine globale Root-CA**.  
  Länder, Organisationen und Unternehmen betreiben **eigene PKIs** zur Wahrung der Kontrolle.  
- Root-[[Zertifikate]] großer CAs sind häufig **in Software integriert** (z. B. Browser).  
- **Vertrauenswürdigkeit** hängt von den **PKI-Dokumentationen** (CP, CPS) ab, die Regeln und Prüfverfahren festlegen.

# Schutz der Root-CA
---
- **Höchste Sicherheitsstufe**, da der Verlust des privaten Schlüssels das gesamte System kompromittiert.  
- **Physischer Schutz** durch Zugangsbeschränkung, Vier- oder Mehr-Augen-Prinzip.  
- **Offline-Betrieb** ohne Netzwerkverbindung.  
- **Manipulationsschutz**: bei Öffnung oder Erschütterung automatische **Löschung der Schlüssel**.  
- **Schlüsselzeremonie** für die Erzeugung und Signierung von Unterschlüsseln nach definierten Protokollen.  
- **Backup und Wiederherstellung** durch Aufteilung des Root-Schlüssels auf mehrere Personen (Schlüsselaufteilung).

# Gültigkeitsdauer
---
- **Root-[[Zertifikate]]:** mehrere Jahre bis Jahrzehnte.  
- **Unterzertifikate:** kürzere Laufzeiten (Monate bis wenige Jahre) zur Minimierung des Risikos kompromittierter Schlüssel.  
- Die Laufzeiten werden so gewählt, dass **aktuelle Rechenkapazitäten** keine Schlüssel innerhalb der Gültigkeit brechen können.

**Ergebnis:** 
Eine **hierarchische Vertrauenskette**, die vom **Root-Zertifikat** ausgeht und über mehrere Ebenen von **Zertifizierungsstellen (CAs)** bis zu den Endzertifikaten reicht.  
Die Integrität dieser Kette ist Grundlage für das Vertrauen in digitale Identitäten innerhalb der PKI.
