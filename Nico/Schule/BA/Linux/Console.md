---
tags:
Fach: "[[BA]]"
Thema:
  - "[[Linux]]"
---
# Allgemein
---
**`arch`** — CPU-Architektur
**`uname`** — Kernel & Systeminfos · `-a` alles · `-r` Kernel-Version
**`lscpu`** — Detaillierte CPU-Infos
**`clear`** — Terminal leeren · auch `Ctrl+L`
**`sudo`** — Als root ausführen · `sudo -i` root-Shell
**`history`** — Befehlsverlauf · `!!` letzten · `!231` Nr. 231 wiederholen
**`ps`** — Prozesse anzeigen · `-e` alle · `-f` ausführlich · `ps aux` Standard
**`pstree -p`** — Prozesse als Baumstruktur mit PIDs
**`kill -9 <PID>`** — Prozess beenden · `-9` erzwingen · `-15` sauber (Standard)
**`killall firefox`** — Alle Prozesse mit diesem Namen beenden
**`htop`** — Interaktiver Prozess-Monitor
  
**`wget`** — Datei herunterladen · `-O` Name · `-q` leise · `-c` fortsetzen
```bash
wget -O datei.zip URL
```
  
**`curl`** — Daten von/zu URL · `-L` Redirects · `-O` speichern · `-I` nur Header
```bash
curl -LO URL
```

**`rfkill`** — Funkschnittstellen ein-/ausschalten
```bash
rfkill list
rfkill block wifi # auch: bluetooth, all
rfkill unblock all
```  

**`tar`** — Entpacken eines tar-Archivs · 
`-x` entpacken
`-z` gzip 
`-f` Datei 
-C` Zielverzeichnis
```bash
tar -xzf datei.tar.gz # Entpacken im aktuellen Verzeichnis
tar -xzf datei.tar.gz -C /pfad/ziel # Entpacken in ein bestimmtes Verzeichnis
tar -tzf datei.tar.gz # Inhalt des Archivs anzeigen (ohne zu entpacken)
tar -czf archiv.tar.gz verzeichnis/ # Archiv erstellen (komprimiert)
``` 
# Speicher & Ressourcen
---
**`free -h`** — RAM-Nutzung
**`top`** — Systemauslastung live (interaktiv)
**`df -h`** — Belegter Speicher der Dateisysteme
**`du`** — Speicherbedarf von Dateien/Ordnern · `-h` lesbar · `-s` Summe · `--max-depth=1`
```bash
du -sh * # Größe aller Elemente im aktuellen Verzeichnis
```
**`lsblk`** — Blockgeräte (Festplatten, Partitionen)
# Netzwerk
---
**`ip`** — Netzwerk-Konfiguration (modern)
```bash
ip a # alle Interfaces & IPs
ip link # Interface-Status
ip route # Routing-Tabelle
```
**`ifconfig`** — Netzwerkinterfaces anzeigen (veraltet, aber noch verbreitet)
**`ping -c 4 8.8.8.8`** — Erreichbarkeit testen · `-c` Anzahl Pakete
  
**`ss`** — Offene Sockets (modernes `netstat`) · `-t` TCP · `-u` UDP · `-l` lauschend · `-n` numerisch
```bash
ss -tlnp
```
  
**`ssh user@host`** — Sicherer Remote-Login · `-p` Port · `-i` Schlüsseldatei
# Variablen & Umgebung
---
```bash
name="Linux" # Variable setzen – kein Leerzeichen um = !
echo $name
echo "Hallo $name" # In Strings: doppelte Anführungszeichen verwenden
  
export name # Für Subprozesse verfügbar machen
unset name # Variable löschen
  
env # Alle Umgebungsvariablen anzeigen
```
  
> **Wichtige Systemvariablen:** `$HOME` · `$PATH` · `$USER` · `$SHELL` · `$PWD`  
# Befehle untersuchen
**`type ls`** — Art eines Befehls (Alias, Builtin, Binary)
**`which python3`** — Pfad zur ausführbaren Datei
**`whereis bash`** — Binär-, Source- und Manpage-Pfade
**`alias ll='ls -la'`** — Eigene Kurzbefehle definieren / anzeigen
**`locate passwd`** — Datei suchen (Datenbank-basiert) · `-i` case-insensitive
**`sudo updatedb`** — Datenbank für `locate` aktualisieren
  
**`man ls`** — Handbuch-Seite · `-f` Kurzbeschreibung
**`info bash`** — Ausführliche GNU-Dokumentation
**`ls --help`** — Kurzreferenz
  
> `man`-Navigation: Suche `/Suchwort` · weiter `n` · zurück `N` · beenden `q`
# Verknüpfungen & Umleitungen
---
```bash
cmd1 ; cmd2 # Nacheinander ausführen (unabhängig voneinander)
cmd1 && cmd2 # cmd2 nur bei Erfolg von cmd1 (Exit-Code 0)
cmd1 || cmd2 # cmd2 nur bei Fehler von cmd1
  
cmd1 | cmd2 # Pipe: Ausgabe von cmd1 als Eingabe für cmd2
cmd > datei # Stdout in Datei schreiben (überschreiben)
cmd >> datei # Stdout in Datei schreiben (anhängen)
cmd < datei # Datei als Eingabe verwenden
cmd 2> datei # Stderr umleiten
cmd &> datei # Stdout + Stderr zusammen umleiten
```
# Navigation
---
**`pwd`** — Aktuelles Verzeichnis anzeigen
**`cd ~/Dokumente`** — Verzeichnis wechseln · `..` hoch · `~` Home · `-` vorheriges
**`ls -lah`** — Verzeichnisinhalt · `-l` Berechtigungen · `-a` versteckt · `-h` Größen · `-R` rekursiv
# Dateien (CRUD)
---
**`touch datei.txt`** — Datei erstellen / Zeitstempel aktualisieren
**`mkdir -p a/b/c`** — Verzeichnis erstellen · `-p` Elternordner mit anlegen
**`cp -r quelle/ ziel/`** — Kopieren · `-i` Nachfragen bei Überschreiben
**`mv alt.txt neu.txt`** — Verschieben / Umbenennen · `-i` Nachfragen
**`rm -rf ordner/`** — Löschen · `-r` rekursiv · `-f` erzwingen
**`ln -s /pfad/ziel linkname`** — Symlink erstellen
  
**`cat datei.txt`** — Inhalt anzeigen / Dateien verketten · `-n` Zeilennummern
**`head -n 5 datei.txt`** — Erste n Zeilen
**`tail -n 5 datei.txt`** — Letzte n Zeilen · `-f` live mitverfolgen (z.B. Logs)
**`nano datei.txt`** — Einfacher Texteditor
**`wc -l datei.txt`** — Zeilen zählen · `-w` Wörter · `-c` Bytes
**`sort -n zahlen.txt`** — Sortieren · `-r` umgekehrt · `-n` numerisch

**`grep`** — Text nach Muster durchsuchen · `-i` case · `-r` rekursiv · `-n` Zeilennr.
```bash
grep -rn "fehler" logs/
grep -i "error" datei.log | tail -20 # kombinierbar mit Pipes
```
**`cut`** — Felder aus Text ausschneiden · `-d` Trenner · `-f` Feld
```bash
cut -d ':' -f 1 /etc/passwd # erste Spalte = Benutzernamen
```
**`find`** — Dateien suchen (live, ohne Datenbank) · `-name` · `-type f/d` · `-size`
```bash
find /home -name "*.log"
find . -type f -name "*.sh" -size +1k
```
# Benutzerverwaltung
---
**`whoami`** — Aktuellen Benutzernamen anzeigen
**`id`** — UID, GID und Gruppen · `id username`

**`adduser max`** — Benutzer anlegen (interaktiv)
**`deluser max`** — Benutzer löschen · `--remove-home` mit Home-Verzeichnis
**`usermod -aG sudo max`** — Zu Gruppe hinzufügen · `-l` für neuen Namen
**`passwd max`** — Passwort setzen · `echo "max:pw" | sudo chpasswd` nicht-interaktiv
  
**`addgroup entwickler`** — Gruppe anlegen
**`delgroup entwickler`** — Gruppe löschen
**`umask 022`** — Standard-Berechtigungen für neue Dateien
  
# Berechtigungen
**`chmod 755 skript.sh`** — Berechtigungen ändern · `+x` ausführbar machen
**`chown user:gruppe datei`** — Besitzer ändern · `-R` rekursiv
**`chgrp gruppe datei`** — Gruppe ändern · `-R` rekursiv
# Skripting (Bash)
---
## Kopf
```bash
#!/bin/bash # Shebang – immer die erste Zeile
```
## Variablen
```bash
name="Welt" # kein Leerzeichen um =
echo "Hallo $name"
zahl=$((3 + 4)) # Arithmetik
```
## Verzweigung
```bash
if [ "$a" -eq 1 ]; then
echo "a ist 1"
elif [ "$a" -gt 1 ]; then
echo "a größer als 1"
else
echo "a ist kleiner"
fi
```
## For-Schleife
```bash
for i in 1 2 3; do
echo "Nr. $i"
done

for datei in *.txt; do # über Dateien iterieren
echo "$datei"
done
```
## While-Schleife
```bash
i=0
while [ "$i" -lt 5 ]; do
echo "$i"
((i++))
done
```
## Funktionen
```bash
greet() {
echo "Hallo $1" # $1 = erstes Argument
}
greet "Max"
```

> **Vergleiche (Zahlen):** `-eq` = · `-ne` ≠ · `-lt` < · `-gt` > · `-le` ≤ · `-ge` ≥
> **Vergleiche (Strings):** `=` · `!=` · `-z` leer · `-n` nicht leer
> **Dateien/Verzeichnisse:** `-f` Datei existiert · `-d` Verzeichnis · `-e` beides