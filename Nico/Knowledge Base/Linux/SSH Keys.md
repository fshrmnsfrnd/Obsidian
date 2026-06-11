---
Thema:
  - "[[Linux]]"
---
>Mit SSH Keys kann man sich das Passwort sparen

# Key Pair erstellen
---
Nur wenn in `~/.ssh/` noch kein Key liegt:
```sh
ssh-keygen -t ed25519 -C "MyComment"
```
`ed25519` ist der gewählte Algorithmus
Speicherort sollte `~/.ssh/id_ed25519` sein
# Key auf den Server kopieren
---
```sh
ssh-copy-id user@host
```
Den Benutzer den du auf dem Server hast und der Hostname oder die IP des Servers.
Es gibt dann noch eine Passwortabfrage.
Trägt den Key automatisch auf dem Server in `~/.ssh/authorized_keys` ein
# SSH Config anlegen
---
Unter `~/.ssh/` die Datei `config` anlegen
Format für Hosts in der Datei:
```txt
Host <YourNameForTheServer>
	HostName <HostnameOrIP>
	User <Username>
	IdentityFile <PrivateKeyPath z.B. ~/.ssh/id_ed25519>
```
# Verbinden
---
```sh
ssh <YourNameForTheServer>
```
# Passwort für SSH auf Server deaktivieren
---
In `/etc/ssh/sshd_config` auf dem Server `PasswordAuthentication no` setzen