---
Thema:
  - "[[Networks]]"
---
# Mehrere Schnittstellen auf einmal auswählen
| Command                            | Description                                |
| ---------------------------------- | ------------------------------------------ |
| `SWITCH (config)# interface range Fa0/1-24 ` | Umschalten aus globalem Konfigurationsmodus |
| `SWITCH (config-if-range)#` | Befehle werde auf alle ausgewählten Schnittstellen übertragen |

# Beschreibung, Duplexmodus, Bandbreite
| Command                            | Description                                |
| ---------------------------------- | ------------------------------------------ |
| `SWITCH (config)# interface FastEthernet 0/1 ` | Umschalten aus globalem Conf.-modus |
| `SWITCH (config-if)# description XXX` | Schnittstellenbeschreibung |
| `SWITCH (config-if)# duplex full` | Duplexmodus (auto, full, half) |
| `SWITCH (config-if)# speed 100` | Bandbreite in Mbps (auto, 10,100) |
| `SWITCH (config-if)# mdix auto` | X-over automatisch erkennen |

# Switch-Schnittstelle zu VLAN zuordnen
| Command                            | Description                                |
| ---------------------------------- | ------------------------------------------ |
| `SWITCH (config-if)# switchport mode access` | Modus der Schnittstelle |
| `SWITCH (config-if)# switchport access vlan 20` | Modus der Schnittstelle zu VLAN 20 zuordnen |

# Port Security
| Command                            | Description                                |
| ---------------------------------- | ------------------------------------------ |
| `SWITCH (config-if)# switchport mode access` | Modus der Schnittstelle |
| `SWITCH (config-if)# switchport port-security` | Port-Security aktivieren |
| `SWITCH (config-if)# switchport port-security maximum 5` | maximal 5 MAC-Adressen |
| `SWITCH (config-if)# switchport port-security mac-address aaaa. aaaaa. aaaa` | statische MAC-Adresse |
| `SWITCH (config-if)# switchport port-security mac-address sticky` | MAC-Adressen dynamisch lernen |
| `SWITCH (config-if)# switchport port-security violation shutdown` | Aktion (restrict, protect) |

# Port deaktivieren
| Command                        | Description |
| ------------------------------ | ----------- |
| `SWITCH (config-if)# shutdown` |             |
