---
Thema:
  - "[[Linux]]"
  - "[[Networks]]"
---
Mit `iperf3` kann die Bitrate zwischen zwei Geräten gemessen werden. Auf beiden muss iperf installiert sein. Eines der Geräte muss den Server starten, und das andere kann dann den Test starten.

# Installation
---
## Windows
https://github.com/ar51an/iperf3-win-builds

Nach dem entpacken der zip muss in der CLI entweder in das Verzeichnis gewechselt werden oder das Verzeichnis zu PATH hinzugefügt werden.
## Linux (apt)
```bash
sudo apt install iperf3
```

# Server starten
---
```Shell
iperf3 -s
```

# Test starten
---
```Shell
iperf3 -c <ip-adress-of-server>
```
