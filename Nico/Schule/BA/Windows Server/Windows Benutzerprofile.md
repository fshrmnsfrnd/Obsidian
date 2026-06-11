---
Fach: "[[BA]]"
Thema:
  - "[[Microsoft]]"
  - "[[Schule/BA/Windows Server/Windows Server|Windows Server]]"
  - "[[Windows Client]]"
---
# Was ist ein Benutzerprofil?
---
Jeder Benutzer hat in Windows ein **Profil**. Das ist ein Ordner welcher alle **Einstellungen** und standardmäßig auch **Daten** speichert. Dieses Profil wird automatisch beim Anmelden unter dem Pfad `%systemdrive%\Users\%username$` erstellt. (Außer der Pfad wird geändert!)
# Ordner im Profil
---
In diesem Profil-Ordner findet man weitere Ordner für verschiedene Arten an Dateien.
![](https://sven.ziegler.page/assets/image_1770483140998_0.png "image.png")
Zu den ganzen sichtbaren Ordnern gibt es auch einen Versteckten `AppData`-Ordner für Programme und eine versteckte `NTUSER.DAT`-Datei in der die Windows Einstellungen gespeichert sind.  
  
Besondere lokale Profile sind:  
-> **Default:** Versteckter Ordner der als Kopiervorlage für neue Benutzerprofile dient  
-> **Public:** Ordner für Datenaustausch unter Benutzern  

Profile welche mit einem Microsoft-Konto verknüpft sind können automatisch über die Microsoft-Server zwischen verschiedenen Rechnern synchronisiert werden. Dies ist in den meisten Firmennetzen deaktiviert!  
# Roaming Profile
---
Wenn ein User sich auf verschiedenen Clients anmelden können soll und immer seine Daten vorfinden soll, können sogenannte **Roaming Profile** eingerichtet werden. Dabei wird das Profil auf einem Share zentral auf einem Server abgelegt. Beim Ab- und Anmelden des Users wird dann sein Profil zum Server gesynced.
# Profil Versionen
---
Alle paar Jahre ändert Microsoft Inhalte der Benutzerprofile. Daher gibt es viele verschieden Versionen. Welche Version welches Profil ist erkennt man an der ändung des Profil-Ordners:  
-> **.V3:** Windows 8  
-> **.V5:** Bis Windows 10 1607  
-> **.V7:** Windows 11  
Wenn sich ein Benutzer an einem Client angemeldet wird automatisch ein Profil mit der niedrigsten vom Client unterstützen Version angelegt. Wenn er sich dann an einem Client mit neuerem Profil anmeldet werden seine Daten **einmalig** synchronisiert.  
Es gibt keinen von Microsoft vorgesehenen Weg um verschiedene Profil-Versionen synchron zu halten!  
Um dieses Problem ein bisschen zu mildern könnte man Ordner (z. B. Dokumente) auf ein anderes (Netz-) Laufwerk weiterleiten.  

Wenn ein Domänenbenutzer gelöscht wird, werden nicht automatisch die Daten auf dem Server, noch den Clients gelöscht (Profil/Home-Laufwerk).  
Damit man diese nachträglich löschen kann muss man sich selber auf den Ordner und alle Unterordner Rechte zum löschen geben!  
# Home-Laufwerk
---
Normalerweise bekommt jeder User auch ein **privates Netzlaufwerk** als Home-Ordner zugewiesen. Dies ist eine smb-Freigabe von einem Server auf den nur dieser eine User Zugriff hat.