---
Thema:
  - "[[Operating System]]"
  - "[[Linux]]"
---
# Fingerabdruck für sudo – Framework 13 + Kubuntu
## Pakete installieren

```bash
sudo apt install fprintd libpam-fprintd
```
## Fingerabdruck einlernen
```bash
fprintd-enroll $USER
```
Oder GUI: Systemeinstellungen → Benutzer → Fingerabdruck-Authentifizierung
## PAM aktivieren
```bash
sudo pam-auth-update
```
→ „Fingerprint authentication" mit Leertaste aktivieren → OK
Das trägt fprintd automatisch in `/etc/pam.d/common-auth` ein.
## Testen
```bash
fprintd-verify $USER        # Sensor-Test
sudo -k && sudo echo "test" # sudo-Test
psexec bash #Popup Test
```
## Pitfalls
- **Nicht** manuell eine `pam_fprintd`-Zeile in `/etc/pam.d/sudo` eintragen – `pam-auth-update` erledigt das über `common-auth`, sonst steht `fprintd` doppelt drin und sudo schlägt fehl.
- Bei `verify-no-match`: Finger neu einlernen mit variierenden Winkeln, vorher `fprintd-delete $USER`