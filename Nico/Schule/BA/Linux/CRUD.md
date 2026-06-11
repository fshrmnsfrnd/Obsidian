---
tags:
Fach: "[[BA]]"
Thema:
  - "[[Linux]]"
---
>CRUD = Create Read Update Delete

# Create

## Benutzer erstellen
[[Console#adduser]]
`sudo adduser <Username>`

[[User (Linux)|Eigenschaften]]

### Adduser ohne Interaktion

`sudo adduser -c`

## Gruppe erstellen
[[Console#addgroup]]
`sudo addgroup <gruppenname>`

# Read

## [[User (Linux)]] anzeigen

`cat /etc/passwd`

## Gruppen anzeigen

`cat /etc/group`

# Update

## [[User (Linux)]] einer Gruppe hinzufügen
[[Console#adduser]]
`sudo adduser <user> <group>`

## eigenes Passwort ändern
[[Console#passwd]]
`passwd`

## anderes Passwort ändern

### interaktiv

`sudo passwd <user>`

### ohne Interaktion
[[Console#chpasswd]]
`sudo chpasswd <<< "<user>:<password>"`

## verschiedene Einstellungen
[[Console#usermod]]
`sudo usermod [-options] <user>`

# Delete

## [[User (Linux)]] löschen
[[Console#deluser]]
`sudo deluser <user>`

## Gruppe löschen
[[Console#delgroup]]
`sudo delgroup <group>`