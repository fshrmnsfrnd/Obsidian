---
Thema:
  - "[[Networks]]"
---
# Modi
![[Pasted image 20260306100535.png]]

| Command                      | Description                                |
| ---------------------------- | ------------------------------------------ |
| `ROUTER> enable`             | Wechseln in EXEC Mode                      |
| `ROUTER# configure terminal` | Umschalten in globalen Konfigurationsmodus |
# Alte Config löschen

| Command                         | Description                |
| ------------------------------- | -------------------------- |
| `ROUTER# erase startup-config`  | Startkonfiguration löschen |
| `ROUTER# reload`                | neu booten                 |
# Hostname
| Command                        | Description                                |
| ------------------------------ | ------------------------------------------ |
| `ROUTER(config)# hostname XXX` | Hostname setzen                            |
# Anfragen an DNS Server verbieten
| Command                               | Description                      |
| ------------------------------------- | -------------------------------- |
| `ROUTER(config)# no ip domain-lookup` | Anfragen an DNS Server verbieten |
# Anmeldebanner

| Command                              | Description   |
| ------------------------------------ | ------------- |
| `ROUTER(config)# banner modt #TEXT#` | Anmeldebanner |
# Hosttabelle
| Command                                      | Description                        |
| -------------------------------------------- | ---------------------------------- |
| `ROUTER(config)# ip host NAME 192.168.17.12` | Eintrag zur Hosttabelle hinzufügen |
#  Passwörter vergeben
## Passwörter für privilegierten Modus

| Command                               | Description                         |
| ------------------------------------- | ----------------------------------- |
| `ROUTER(config)# enable secret XXX`   | verschlüsseltes Passwort vergeben   |
| `ROUTER(config)# enable password XXX` | unverschlüsseltes Passwort vergeben |
## Konsole absichern

| Command                                     | Description                                |
| ------------------------------------------- | ------------------------------------------ |
| `ROUTER (config)# line console 0`           | Umschalten in Konsolen-Konfigurationsmodus |
| `ROUTER (config-line)# password XXX`        | Passwort vergeben                          |
| `ROUTER (config-line)# login`               | Benutzer muss sich anmelden                |
| `ROUTER (config-line)# logging synchronous` | Logmeldungen in extra Zeile                |
## Telnet absichern

| Command                              | Description                                        |
| ------------------------------------ | -------------------------------------------------- |
| `ROUTER (config)# line vty 0 4`      | Umschalten in Telnet-Konfigurationsmodus (0-15!!!) |
| `ROUTER (config-line)# password XXX` | Passwort vergeben                                  |
| `ROUTER (config-line)# login`        | Benutzer muss sich anmelden                        |
## alle unverschlüsselten Passwörter (auch nachträglich) verschlüsseln
| Command                                        | Description                          |
| ---------------------------------------------- | ------------------------------------ |
| `ROUTER (config)# service password-encryption` | Verschlüsselt und sichert Passwörter |
# Netzwerkschnittstellen
## Ethernet
| Command                                                        | Description                         |
| -------------------------------------------------------------- | ----------------------------------- |
| `ROUTER (config)# interface GigabitEthernet0/0/0 `             | Umschalten aus globalem Conf.-modus |
| `ROUTER (config-if)# description XXXX `                        | Beschreibung                        |
| `ROUTER (config-if)# ip address 192.111.111.111 255.255.255.0` | IP/SM einstellen                    |
| `ROUTER (config-if)# no shutdown`                              | Interface aktivieren                |
## Seriell
| Command                                                         | Description                                 |
| --------------------------------------------------------------- | ------------------------------------------- |
| `ROUTER (config)#interface Serial0/0`                           | Umschalten aus globalem Konfigurationsmodus |
| `ROUTER (config-if)# description XXXX`                          | Beschreibung                                |
| `ROUTER (config-if)# ip address 192.111.111.111 255.255.255. 0` | IP/SM einstellen                            |
| `ROUTER (config-if)# clock rate 56000`                          | Clockrate einstellen (nur bei DCE!)         |
| `ROUTER (config-if)# no shutdown`                               | Interface aktivieren                        |
## Loopback
| Command                                                        | Description                                 |
| -------------------------------------------------------------- | ------------------------------------------- |
| `ROUTER (config)# interface loopback 0`                        | Umschalten aus globalem Konfigurationsmodus |
| `ROUTER (config-if)# ip address 192.168.31.33 255.255.255.255` | IP/SM einstellen                            |
# Konfiguration speichern
| Command                                      | Description                                        |
| -------------------------------------------- | -------------------------------------------------- |
| `ROUTER# copy running-config startup-config` | aktive Konfiguration →> Startkonfiguration (NVRAM) |
# TFTP-Server
| Command                            | Description                         |
| ---------------------------------- | ----------------------------------- |
| `ROUTER# copy running-config tftp` | aktive Konfiguration -> TFTP-Server |
| `ROUTER# copy startup-config tftp` | Startkonfiguration -> TFTP-Server   |
| `ROUTER# copy tftp startup-config` | TFT-Server - Startkonfiguration     |
# show
| Command                             | Description                                   |
| ----------------------------------- | --------------------------------------------- |
| `ROUTER# show version`              | IOS-Version, Platform, Konfigurationsregister |
| `ROUTER# show flash:`               | IOS-Abbild, Speicherplatz                     |
| `ROUTER# show running-config`       | aktuelle Konfiguration                        |
| `ROUTER# show startup-config`       | Startkonfiguration                            |
| `ROUTER# show ip interface brief`   | kurze Schnittstellenbeschreibung              |
| `ROUTER# show interfaces`           | ausführliche Schnittstellenbeschreibung       |
| `ROUTER# show controllers serial 0` | serielles Kabel DCE/DTE                       |
| `ROUTER# show hosts`                | Hosttabelle                                   |
| `ROUTER# show arp`                  | ARP-Tabelle                                   |
| `ROUTER# show users`                | angemeldete Benutzer                          |
| `ROUTER# show clock`                | Datum und Uhrzeit                             |
| `ROUTER# show protocols`            | Layer 3 Protokolle                            |
