---
Fach:
tags:
Thema:
  - "[[Webentwicklung]]"
---
### Webserver Beispiele
- Apache
- [[NGINX]]
- Microsoft IIS

# Konfigurationsdateien
- Kommentarzeichen: # 

## Wichtige Direktiven
>Direktive: Schlüsselwort gefolgt von Wert(en)

| Direktive      | Beschreibung                                                                                                                  | Beispiel                                         |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| Include        | Fügt ein Config-File ein                                                                                                      | `Include conf/extra/httpd-vhosts.conf`           |
| ServerName     | Gibt den Haupt-Domainnamen oder die IP-Adresse des Servers an, auf die Apache reagieren soll.                                 | `ServerName www.example.com`                     |
| DocumentRoot   | Legt das Verzeichnis fest, in dem die HTML-Dateien und anderen Webinhalte für den Server gespeichert sind.                    | `DocumentRoot "/var/www/html"`                   |
| Listen         | Gibt die Portnummer und/oder IP-Adresse an, auf die Apache eingehende Anfragen akzeptiert.                                    | `Listen 80`                                      |
| AllowOverride  | Bestimmt, ob .htaccess-Dateien verwendet werden dürfen, um die Konfiguration für ein bestimmtes Verzeichnis zu überschreiben. | `AllowOverride All`                              |
| Options        | Legt fest, welche Funktionen in einem bestimmten Verzeichnis erlaubt sind (z. B. Directory-Listing, SymLinks).                | `Options Indexes FollowSymLinks`                 |
| DirectoryIndex | Gibt die Standarddateien an, die Apache lädt, wenn kein spezifischer Dateiname angegeben ist.                                 | `DirectoryIndex index.html index.php`            |
| RewriteEngine  | Aktiviert die URL-Umschreibung, oft verwendet, um benutzerfreundlichere URLs zu erstellen.                                    | `RewriteEngine On`                               |
| RewriteRule    | Definiert spezifische Regeln für die URL-Umschreibung, z. B. Weiterleitungen oder Umstrukturierungen.                         | `RewriteRule "^/oldpage$" "/newpage" [R=301,L]`  |
| Alias          | Erlaubt die Zuordnung eines URL-Pfades zu einem anderen Verzeichnispfad im Dateisystem.                                       | `Alias /images "/var/www/images"`                |
| ErrorLog       | Pfad zur Logdatei für Fehlermeldungen                                                                                         | `ErrorLog /var/log/httpd/error_log`              |
| CustomLog      | Pfad für die Logdatei in der alle Requests aufgezeichnet werden.                                                              | `CustomLog "/var/log/httpd/access_log" combined` |
## Gültigkeitsbereich von Direktiven

| Abschnittbezeichnung | Erklärung |
| -------------------- | --------- |
| `<Directory>`        |           |
| `<DirectoryMatch>`   |           |
| `<Files>`            |           |
| `<FilesMatch>`       |           |
| `<Location>`         |           |
| `<LocationMatch>`    |           |

