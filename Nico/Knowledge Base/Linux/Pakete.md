---
Thema:
  - "[[Linux]]"
  - "[[Operating System]]"
---
>Überblick über alle Paketformate unter Kubuntu (apt, Flatpak, Snap, `.deb`, AppImage), wann man welches nimmt, wo sie landen und wie man Repos zu `apt` hinzufügt.
# Überblick & Entscheidung
---

| Format | Typ | Quelle | Updates | Sandbox | Wann nehmen |
| ------ | --- | ------ | ------- | ------- | ----------- |
| **apt** | Systempaket (`.deb` aus Repo) | Ubuntu-Repos / PPAs | zentral (`apt upgrade`) | nein | Standard für alles, was es im Repo gibt; CLI-Tools, Bibliotheken, Treiber |
| **Flatpak** | Sandbox-App | Flathub | pro App (`flatpak update`) | ja | Desktop-Apps, neueste Versionen, distro-unabhängig |
| **Snap** | Sandbox-App | Snap Store (Canonical) | automatisch | ja | wenn nur als Snap verfügbar (selten nötig) |
| **`.deb`** | Systempaket (Datei) | Hersteller-Download | nur wenn eigenes Repo mitkommt | nein | Hersteller-Software ohne Repo (Chrome, VS Code) |
| **AppImage** | portable Datei | Hersteller-Download | manuell / via Tool | teilweise | einmalig testen, portabel, kein Root nötig |

> [!TIP] Faustregel
> Zuerst **apt**. Gibt es das Paket dort nicht oder ist es zu alt → **Flatpak** (Flathub). **Snap** nur wenn unvermeidbar. **`.deb`** vom Hersteller, wenn ein eigenes Repo mitkommt (dann updatet es über apt mit). **AppImage** für „mal eben ausprobieren" oder portabel.
# apt
---
>**APT** steht für **A**dvanced **P**ackage **T**ool. Verwaltet `.deb`-Pakete aus konfigurierten Repos inkl. Abhängigkeiten.
## Grundbefehle
```bash
sudo apt update              # Paketlisten aktualisieren (Metadaten)
sudo apt upgrade             # installierte Pakete aktualisieren
sudo apt full-upgrade        # auch Pakete entfernen/ersetzen wenn nötig
sudo apt install <paket>
sudo apt remove <paket>      # Paket entfernen, Configs bleiben
sudo apt purge <paket>       # Paket + Configs entfernen
sudo apt autoremove          # nicht mehr benötigte Abhängigkeiten weg
apt search <begriff>
apt show <paket>             # Details, Version, Abhängigkeiten
apt list --installed
```
## Wo apt installiert
Folgt dem **FHS** (**F**ilesystem **H**ierarchy **S**tandard), systemweit:

| Ort | Inhalt |
| --- | ------ |
| `/usr/bin`, `/usr/sbin` | ausführbare Programme |
| `/usr/lib` | Bibliotheken |
| `/usr/share` | architekturunabhängige Daten (Icons, Docs, `.desktop`) |
| `/etc` | systemweite Konfiguration |
| `/var` | veränderliche Daten (Logs, DBs, Caches) |
Welche Dateien ein Paket angelegt hat: `dpkg -L <paket>`. Welches Paket eine Datei besitzt: `dpkg -S /pfad/datei`.
# Repos zu apt hinzufügen
---
Repos stehen in `/etc/apt/sources.list` und in einzelnen `.list`/`.sources`-Dateien unter `/etc/apt/sources.list.d/`. Jedes externe Repo braucht einen **GPG-Schlüssel** zur Signaturprüfung (liegt unter `/etc/apt/keyrings/` bzw. `/usr/share/keyrings/`).
## Variante 1: PPA (Ubuntu Personal Package Archive)
```bash
sudo add-apt-repository ppa:<benutzer>/<ppa>
sudo apt update
sudo apt install <paket>
```
Schlüssel und Quelle werden automatisch eingetragen. Entfernen mit `--remove`:
```bash
sudo add-apt-repository --remove ppa:<benutzer>/<ppa>
```

> [!WARNING] PPAs mit Bedacht
> PPAs sind von Einzelpersonen gepflegt, ungeprüft und können das System destabilisieren. Nur vertrauenswürdige nutzen.
## Variante 2: Drittanbieter-Repo manuell (moderne Methode)
Schlüssel **nicht** mehr mit `apt-key` (deprecated), sondern als Datei in `/etc/apt/keyrings/` ablegen und im Repo per `signed-by` referenzieren. Beispiel (VS Code):
```bash
# 1. Schlüssel holen und ablegen
wget -qO- https://packages.microsoft.com/keys/microsoft.asc \
  | gpg --dearmor | sudo tee /etc/apt/keyrings/microsoft.gpg > /dev/null

# 2. Repo-Eintrag anlegen
echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/microsoft.gpg] \
https://packages.microsoft.com/repos/code stable main" \
  | sudo tee /etc/apt/sources.list.d/vscode.list

# 3. Aktualisieren und installieren
sudo apt update && sudo apt install code
```
Aufbau einer `deb`-Zeile: `deb [optionen] <URL> <suite> <komponenten>`, z.B. `deb https://... noble main`. `noble` = Ubuntu-Codename (Kubuntu 24.04), per `lsb_release -cs` herauszufinden.

> [!IMPORTANT] Vorteil eigenes Repo
> Software aus einem Hersteller-Repo (Chrome, VS Code) wird bei `apt upgrade` **automatisch mitaktualisiert** – im Gegensatz zu einer manuell installierten `.deb`-Datei.
# .deb-Dateien (manuell)
---
Einzelne `.deb` vom Hersteller herunterladen und installieren. Empfohlen mit `apt`, weil es Abhängigkeiten auflöst:
```bash
sudo apt install ./programm.deb     # ./ ist wichtig (sonst sucht apt im Repo)
```
Alternativ klassisch mit `dpkg` (löst **keine** Abhängigkeiten auf):
```bash
sudo dpkg -i programm.deb
sudo apt install -f                 # fehlende Abhängigkeiten nachziehen
```
Landet wie apt-Pakete systemweit unter `/usr` etc. Updates nur, wenn das `.deb` ein eigenes Repo eingerichtet hat – sonst manuell neue Version nachladen.
# Flatpak
---
Sandboxed Desktop-Apps, distro-unabhängig, parallel installierbare Versionen. Auf Kubuntu nicht vorinstalliert.
## Einrichten
```bash
sudo apt install flatpak
sudo apt install plasma-discover-backend-flatpak   # Flatpak in Discover
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
# danach einmal neu anmelden/neustarten
```
## Benutzung
```bash
flatpak install flathub org.videolan.VLC
flatpak run org.videolan.VLC
flatpak update
flatpak list
flatpak uninstall org.videolan.VLC
flatpak uninstall --unused           # ungenutzte Runtimes entfernen
```
## Wo Flatpak installiert
| Ort | Bedeutung |
| --- | --------- |
| `/var/lib/flatpak/` | systemweite Installation (`--system`, Standard mit sudo) |
| `~/.local/share/flatpak/` | nur für den Benutzer (`--user`, kein Root nötig) |
| `~/.var/app/<app-id>/` | App-Daten/Configs pro App (sandbox-Home) |

Apps haben eine umgekehrte Domain-ID (`org.videolan.VLC`). Sandbox-Rechte (z.B. Dateizugriff) mit dem Tool **Flatseal** verwalten.

> [!NOTE] Größe
> Flatpaks bringen eigene Runtimes/Bibliotheken mit → mehr Speicher, dafür unabhängig von Systembibliotheken. Runtimes werden zwischen Apps geteilt.
# Snap
---
Canonicals Sandbox-Format. Auf Ubuntu-Servern Standard, auf **Kubuntu standardmäßig nicht** vorinstalliert. Updates laufen automatisch.
```bash
sudo apt install snapd
sudo snap install <paket>
sudo snap install <paket> --classic   # ohne Sandbox-Einschränkung (z.B. IDEs)
snap list
sudo snap refresh                      # alle aktualisieren
sudo snap remove <paket>
```
Mountpunkt der Pakete: `/snap/`, Daten unter `/var/snap/` und `~/snap/`. Jedes Snap erscheint als Loop-Device in `lsblk` (normal).

> [!WARNING] Wann Snap
> Nur nutzen, wenn Software ausschließlich als Snap angeboten wird. Nachteile: automatische Updates schwer kontrollierbar, langsamerer Start, ein zentraler Store (Canonical). Für Desktop-Apps ist Flatpak meist die bessere Wahl.
# AppImage
---
Eine einzelne ausführbare Datei, die die App samt Abhängigkeiten bündelt. Keine Installation, kein Root nötig – ideal zum Testen oder portabel (USB-Stick).
```bash
chmod +x programm.AppImage    # ausführbar machen
./programm.AppImage           # starten
```
Speichern z.B. unter `~/Applications/` oder `~/.local/bin/`. Es gibt **keine** automatische Menü-Integration und **keine** Updates von Haus aus.

> [!TIP] Integration & Updates
> Tool **Gear Lever** (als Flatpak) integriert AppImages ins Anwendungsmenü und verwaltet Updates. Manche AppImages bringen einen eigenen Updater mit (`--appimage-update`).
# Schnellvergleich der Installationsorte
---

| Methode | Scope | Pfad (Programm) | Root nötig | Auto-Update |
| ------- | ----- | --------------- | ---------- | ----------- |
| apt / `.deb` | systemweit | `/usr/bin` | ja | ja (über Repo) |
| Flatpak `--system` | systemweit | `/var/lib/flatpak` | ja | nein (manuell/Discover) |
| Flatpak `--user` | nur User | `~/.local/share/flatpak` | nein | nein (manuell) |
| Snap | systemweit | `/snap` | ja | ja (automatisch) |
| AppImage | beliebig | frei wählbar | nein | nein |
