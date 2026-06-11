---
Fach: "[[BA]]"
Thema:
  - "[[Microsoft]]"
  - "[[Schule/BA/Windows Server/Windows Server|Windows Server]]"
---
Der DHCP-Server Konfiguriert beim Client:  
- **IP-Adresse**  
- **Subnetzmaske**  
- **[[DNS]]-Server**  
- **Default Gateway**    
Per Default nimmt der Windows-Nameserver nur dynamische Einträge für Domänenmitglieder vor. Der Windows DHCP-Server nimmt **keine** [[DNS]]-Einträge vor. Diese Einstellungen können geändert werden! Der Windows Client trägt seinen FQDN/Hostname und seine IP selbst beim [[DNS]] ein.
# Ausfallsichere DHCP Server
---
Normalerweise erstellt man zwei DHCP-Server in einem Netz und teilt den DHCP-Adressraum auf die beiden Server gleichmäßig auf. Seit [[Schule/BA/Windows Server/Windows Server]] 2012 kann man aber eine Replikation zwischen DHCP-Servern einrichten.  
Damit man so eine Replikation erstellen kann muss man min. zwei **Member-Server** zu einem AD hinzufügen.  
Anschließend wird auf einem Server die Rolle **DHCP-Server** hinzugefügt. Nach der Installation muss man noch seinen DHCP-Dienst konfigurieren:  
- Adressbereich  
- Ausschlüsse, Verzögerungen, Lease Dauer  
- Gateway  
- Übergeordnete Domäne  
- [[DNS]]-Server  
Nun wird der zweite DHCP-Server eingerichtet. Es wird wieder die Rolle installiert, aber **kein** neuer Bereich festgelegt!  
Man wählt den Bereich des ersten Servers aus und richtet ihn als **Failover** ein.  
Dabei kommen folgend Begriffe vor:  
- **Maximale Clientvorlaufzeit:** Maximale Zeit um die der DHCP-Lease verlängert werden kann, als dem Failover System bekannt ist  
- Modus:  
	- **Lastenausgleich:** Die Last der DHCP-Anfragen wird auf alle Server verteilt  
	- **Hot Standby:** Ein Server steht nur aktiv da im Fall das der andere ausfällt  
- **Interval für Zustands-Switchover:** Zeit, nach der der DHCP Server in den Status "**Partner Down**" wechselt (Default 60min)