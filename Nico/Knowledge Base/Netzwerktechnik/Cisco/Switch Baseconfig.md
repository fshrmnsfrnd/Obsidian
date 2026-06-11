---
Thema:
  - "[[Networks]]"
---
# Alte Config löschen

| Command                         | Description                |
| ------------------------------- | -------------------------- |
| `SWITCH# delete flash:vlan.dat` | VLANs löschen              |
| `SWITCH# erase startup-config`  | Startkonfiguration löschen |
| `SWITCH# reload`                | neu booten                 |
# Hostname
| Command                        | Description     |
| ------------------------------ | --------------- |
| `SWITCH(config)# hostname XXX` | Hostname setzen |
# Anfragen an DNS Server verbieten
| Command                               | Description                      |
| ------------------------------------- | -------------------------------- |
| `SWITCH(config)# no ip domain-lookup` | Anfragen an DNS Server verbieten |
# Anmeldebanner

| Command                              | Description   |
| ------------------------------------ | ------------- |
| `SWITCH(config)# banner modt #TEXT#` | Anmeldebanner |
#  Passwörter vergeben
## für privilegierten Modus

| Command                               | Description                         |
| ------------------------------------- | ----------------------------------- |
| `SWITCH(config)# enable secret XXX`   | verschlüsseltes Passwort vergeben   |
| `SWITCH(config)# enable password XXX` | unverschlüsseltes Passwort vergeben |
## Konsole absichern

| Command                            | Description                                |
| ---------------------------------- | ------------------------------------------ |
| `SWITCH (config)# line console 0`    | Umschalten in Konsolen-Konfigurationsmodus |
| `SWITCH (config-line)# password XXX` | Passwort vergeben                          |
| `SWITCH (config-line)# login`        | Benutzer muss sich anmelden                |

## Telnet absichern

| Command                            | Description                                |
| ---------------------------------- | ------------------------------------------ |
| `SWITCH (config)# line vty 0 15` | Umschalten in Telnet-Konfigurationsmodus (0-15!!!) |
| `SWITCH (config-line)# password XXX` | Passwort vergeben |
| `SWITCH (config-line)# login` | Benutzer muss sich anmelden |

## alle unverschlüsselten Passwörter (auch nachträglich) verschlüsseln
| Command                            | Description                                |
| ---------------------------------- | ------------------------------------------ |
| `SWITCH (config)# service password-encryption | |

# IP-Schnittstelle konfigurieren (nur eine pro Switch)
| Command                            | Description                                |
| ---------------------------------- | ------------------------------------------ |
| `SWITCH (config)# interface vlan 17` | Management-VLAN auswählen |
| `SWITCH (config-if)# ip address 192.111.111.111 255.255.255.0` | IP/SM einstellen |
| `SWITCH (config-if)# no shutdown` | Interface aktivieren |
| `SWITCH (config)# ip default-gateway 192.111.111.254` | Default-Gateway |

# SSH-Server
| Command                            | Description                                |
| ---------------------------------- | ------------------------------------------ |
| `SWITCH (config)# hostname XXX` | wird für Key verwendet |
| `SWITCH (config)# ip domain-name beispiel.de` | wird für Key verwendet |
| `SWITCH (config)# crypto key generate rsa` | Key erzeugen |
| `SWITCH (config)# username NAME` | Benutzer anlegen |
| `SWITCH (config)# line vty 0 15` | Umschalten in Telnet-Konfigurationsmodus (0-15!!!) |
| `SWITCH (config-line)# password XXX` | Passwort vergeben |
| `SWITCH (config-line)# login` | Benutzer muss sich anmelden |
| `SWITCH (config-line)# transport input ssh` |  nur noch SSH zulassen |

# Webinterface aktivieren
| Command                            | Description                                |
| ---------------------------------- | ------------------------------------------ |
| `SWITCH (config)# ip http server` | Webinterface aktivieren |
| `SWITCH (config)# ip http port 80` | Port festlegen |

# MAC-Address-Table
| Command                            | Description                                |
| ---------------------------------- | ------------------------------------------ |
| `SWITCH (config)# mac-address-table static aaaa.aaaa.aaaa vlan 1 interface Fa0/1` | statischer Eintrag |
| `SWITCH# clear mac-address-table dynamic` | CAM löschen |
| `SWITCH# clear port-security` | Secure-Adressen aus CAM löschen|

# Konfiguration speichern
| Command                            | Description                                |
| ---------------------------------- | ------------------------------------------ |
| `SWITCH#copy running-config startup-config ` |aktive Konfiguration->Startkonfiguration (NVRAM) |
| `SWITCH# copy running-configtftp ` |aktive Konfiguration-> TFTP-Server |
| `SWITCH#copy startup-config tftp ` |Startkonfiguration-> TFTP-Server |
| `SWITCH#copy startup-config flash` |Startkonfiguration-> flash |

# Konfiguration laden
| Command                            | Description                                |
| ---------------------------------- | ------------------------------------------ |
| `SWITCH#copy tftp running-config ` | TFTP-Server -> aktive Konfiguration |
| `SWITCH#copy tftpstartup-config ` | TFTP-Server -> Startkonfiguration |

# show
| Command                                              | Description                                    |
| ---------------------------------------------------- | ---------------------------------------------- |
| `SWITCH# show version`                               | IOS-Version, Plattform, Konfigurationsregister |
| `SWITCH# show flash`                                 | IOS-Abbild, vlan.dat                           |
| `SWITCH# show running-config`                        | aktuelle Konfiguration                         |
| `SWITCH# show startup-config`                        | Startkonfiguration                             |
| `SWITCH# show ip interface brief`                    | kurze Schnittstellenbeschreibung               |
| `SWITCH# show interfaces`                            | ausführliche Schnittstellenbeschreibung        |
| `SWITCH# show controllers ethernet-controller Fa0/1` | Traffic-Statistik                              |
| `SWITCH# show mac-address-table`                     | CAM                                            |
| `SWITCH# show vlan`                                  | VLANs mit zugeordneten Ports                   |
| `SWITCH# show port-security interface Fa0/1`         | Port-Security-Status der Schnittstelle         |
| `SWITCH# show port-security address`                 | MAC-Adressen                                   |
# Spanning Tree

| Command                                                     | Description                                                                                 |
| ----------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| `Switch# show running-config \| include spanning-tree mode` | Spanning Tree modus anzeigen: (pvst rapid-pvst mst) (i.A. nicht im Packet Tracer verfügbar) |
| `Switch(config)#spanning-tree mode pvst`                    | STP Modus auswählen                                                                         |
| `Switch#show spanning-tree`                                 | Spanning Tree Details, wie Information zu Root bridge und Port-Stati                        |
| `Switch(config)#spanning-tree vlan 1`                       | STP auf VLAN 1 aktivieren                                                                   |
# EtherChannel

|                                                                                                                                                                                                                                                                                           |                                                                                   |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `Switch(config)#interface FastEthernet1/1 `<br>`Switch(config-if)#channel-protocol lacp`<br>`Switch(config-if)#channel-group 1 mode active`<br>`Switch(config)#interface FastEthernet4/1`<br>`Switch(config-if)#channel-protocol lacp`<br>`Switch(config-if)#channel-group 1 mode active` | Beispiel<br>Interface Fa1/1 und Fa4/1 werden der <br>Channel-Gruppe 1 zugewiesen. |
| `Switch#show etherchannel summary`                                                                                                                                                                                                                                                        | EtherChannel überprüfen                                                           |
| `Switch(config)#interface fastEthernet1/1` <br>`Switch(config-if)#no channel-group 1`                                                                                                                                                                                                     | EtherChannel deaktivieren                                                         |
