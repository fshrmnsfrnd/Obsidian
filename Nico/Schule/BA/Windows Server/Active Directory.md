---
Fach: "[[BA]]"
Thema:
  - "[[Microsoft]]"
  - "[[Schule/BA/Windows Server/Windows Server|Windows Server]]"
---
Das **Active Directory** oder auch **AD** ist der Verzeichnisdienst von Microsoft und die wichtigste Server-Funktion. Diese Rolle heißt **Active Directory Domain Service** (**ADDS**) und den Server der diesen Dienst anbietet nennt man **Domaincontroller**.  
Ein Verzeichnisdienst dient zur Verwaltung von **Geräten**, **Benutzern** und **Diensten** in einer **Domäne**.
# Protokolle im Zusammenhang mit AD
---
- LDAP (Lightweight Directory Access Protocol) vor allem für Benutzerdaten (weit verbreitetes Protokoll)
- Kerberos für die Authentifizierung (RFC-Standard)
- SMB (Server Message Block) als Netzwerk-Dateisystem (von Microsoft)
- [[DNS]] (weitgehend nach RFC)
# Alternativen
---
- UCS
- [[Samba]]
# Administratoren Konto
---
Auf einem AD-Controller gibt es zwei Administratoren:  
-> **Wiederherstellungsadministrator:** wird für die Reparatur eins ADs verwendet  
-> **Domänenadministrator:** Dient zur Verwaltung der Domäne  

> [!IMPORTANT] Domänencontroller besitzen **keinen** lokalen Administrator!
# Installation
---
1. Im Server Manager die Rolle Active Directory installieren
2. Mitteilung *Server zum Domänenkontroller heraufstufen* auswählen
3. Stammdomäne (z.B. `tsm.local`) angeben
4. [[DNS]] Server aktivieren
5. Als [[DNS]] sich selbst eintragen
# Hierarchische Struktur des AD
---
![[Pasted image 20260301200006.png]]
**Domäne** (Domain): 
Die Windows-Domäne ist die wichtigste Einheit einer Active-Directory-Struktur. Jede Struktur enthält mindestens eine Domäne. Pro Domäne muss es mindestens einen Domänencontroller (= Server mit AD) geben. Unsere Domäne heißt `<domänenname>.local` und der erste Domänencontroller
`dc1.<domänenname>.local`
Ein Active Directory funktioniert nur dann, wenn es für die Domäne einen funktionieren Nameserver gibt. Es ist üblich, diesen auf dem Domänencontroller laufen zu lassen.

**Unterdomäne** (Subdomain): 
Eine Domäne kann wie im Domain Name System des Internets mehrere Unterdomänen und diese wieder Unterdomänen enthalten. Es entsteht ein Baum (**Tree**). Auch jede Unterdomäne
muss mindestens einen Domänencontroller haben.

**Gesamtstruktur** (**Forest**): 
In einer Active-Directory-Gesamtstruktur können mehrere Bäume aus Domänen verwaltet werden
# Container
---
Ein Active Directory verwaltet wie bereits erwähnt Objekte wie Benutzer und Computer. Diese sind (hierarchisch Strukturiert) in **Containern** angeordnet. Diese findet man in dem Tool **Active Directory-Benutzer und -Computer**.  
Diese Container sind: 
-> **Gesamtstruktur** (**Forest**): Container für **Trees**  
-> **Trees:** Container für **Domänen**  
-> **Domänen:** Container für **Organisationseinheiten** (**OUs**)  
-> **Organisationseinheiten** (**OUs**): Container für **Benutzer**, **Gruppen**, **Computer** und weiteren **OUs**  

OUs sind alle Container bis auf die Domäne selbst und ein paar Standardcontainer, die jede Domäne automatisch enthält. Dabei sind die Relevantesten:  
-> **Builtin:** Container für Gruppen die nur auf dem Domänencontroller gelten.  
-> **Computers:** Hier landen alle **Clients** und **Member Server** welche der Domäne beitreten.  
-> **Domain Controllers:** Container für die **Domaincontroller**.  
-> **Users:** Container für **Benutzer** und **Gruppen** welche Windows automatisch anlegt.
# Benutzergruppen
---
Wenn man eine neue Gruppe erstellen möchte bekommt man folgende Einstellungen:  
- **Gruppenname**  
- **Gruppenbereich:**  
	- **Lokal:** Gruppen auf dem Server (gehören zu keiner Domain)  
	- **Lokal (in Domäne):** Gruppe für die eigene Domäne  
	- **Global:** Gruppe die in der Gesamtstruktur sichtbar ist, enthalten aber nur Benutzer aus einer Domäne  
	- **Universal:** Beinhalten Benutzer und Gruppen aus allen Domänen eines Forests.  
- **Gruppentyp:**  
	- **Verteilung:** wenn es sich um einen E-Mail-Verteiler handelt  
	- **Sicherheit:** für alle Möglichkeiten einer Gruppe  

**OUs** werden verwendet um die **Struktur** eines Unternehmens im AD dazustellen. 
**Gruppen** um die **Rechtevergabe** zu managen!
# Automatische Änderungen am Client bei Domänenaufnahme
---
- Am Anmeldebildschirm kann man Domänenbenutzer eingeben 
- Lokale User nur mit `.\localuser`
- Der Administrator wird immer lokal angemeldet außer man schreibt `domain.name\Administrator` oder `Administrator@domain.name`
- Das primäre **[[DNS]]-Suffix** des Rechners wird automatisch passend zur Domäne eingestellt, bei uns also auf `<domänenname>.local`

> [!NOTE] Jeder Domänennutzer ist 10 mal berechtigt einen Client in die Domäne auf zu nehmen!
# Gruppenrichtlinien
---
**Gruppenrichtlinienobjekte** (**GPOs** = group policy objects) sind zentrale Konfigurationsanweisungen für Benutzer, Gruppen und Computer im AD. Beispiele hierfür sind:  
- automatische Installation von Software-Paketen  
- Umleitung von Ordner  
- angepasstes Aussehen des Desktops  
Dabei kann festgelegt werden wo diese Richtlinien gelten. z. B. Standort, OU, Domäne, ....  
Gruppenrichtlinien können aber auch **lokal** auf einzelnen Computern erstellt werden 
## Vererbung
Gruppenrichtlinien werden an die darunterliegenden OUs vererbt. Diese Vererbung lässt sich deaktivieren. Damit Einstellungen nicht von anderen Richtlinien überschrieben werden, kann man diese **erzwingen**.  

Gruppenrichtlinien werden aktiv wenn der Computer gestartet (**Computerkonfiguration**) wird oder sich ein Benutzer anmeldet (**Benutzerkonfiguration**). GPOs die später geladen werden überschreiben früher geladene:  
1. Lokale GPOs  
2. Standort GPOs  
3. Domänen GPOs  
4. GPOs für OUs von Oben nach Unten in der Hierarchie  
## GPO erstellen
Wenn man ein GPO erstellt hat muss man es anschließend einer oder mehreren OUs zuordnen. (Das GPO wird mit der OU verknüpft, nicht ihr untergeordnet!)  
Dabei wird in einem GPO zwischen **Benutzer** und **Computern** und darin noch mal in **Einstellungen** und **Richtlinien** unterschieden.  
- **Einstellungen:** Vorkonfiguration die von Benutzern oder Administratoren geändert werden können  
- **Richtlinien:** können nicht überschrieben werden  
  
Wenn nur Benutzer- oder Computerkonfigurationen in einem GPO verwendet werden, sollte der andere Part deaktiviert werden um die Aktivierungszeit zu beschleunigen.  
# Default Domain Policy
---
Die **Default Domain Policy** gilt für die ganze Domäne und wird im Normalfall **nicht** verändert. Hier sollten nur Dinge eingestellt werden die wirklich **JEDEN** Benutzer betreffen z. B. die Vorgaben für ein sicheres Passwort.
- Tipps

> [!NOTE] GPOs kann man mit `gpupdate` manuell neu von Server ziehen

# Einen Client in eine Domäne aufnehmen
---
1. Settings/System/About/Advanced system settings/Computer Name
2. Klicke auf ändern
3. Wähl Domain aus und gibt die Domain ein