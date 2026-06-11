---
Fach:
Thema:
  - "[[JavaScript]]"
  - "[[Webentwicklung]]"
---
>Es können generell nur Strings gespeichert werden
# Cookies
---

> [!WARNING] Alle gespeicherten Cookies werde grundsätzlich immer bei jedem Aufruf eine Seite der gleichen Domain an den Server übermittelt. Bei einer schlechten Sicherheitseinstellung können Cookiedaten auch an fremde Domains übertragen werden. Verwenden Sie Cookies nur, wenn die gespeicherten Informationen an den Server übertragen werden sollen.
## Erzeugen
```javascript
let now = new Date()
let time = new Date(a.getTime() + 1000*60*60*24) //aktuelles Datum + Anzahl der tausendstel Sekunde
document.cookie="<key>=<value>;expires=" + time
```
## Lesen
```javascript
let cookiearray = cookietext.split(";")
let keyvalue = cookiearray[i].split("=");
```
# LocalStorage
---
>Daten werden gespeichert, bis sie manuell gelöscht werden
## Speichern
```javascript
localStorage.<key> = <value>
localStorage.setItem(<key>, <value>)
```
## Lesen
```javascript
let value = localStorage.<key>
```
## Löschen
```javascript
localStorage.removeItem(<key>)
```
# SessionStorage
---
>Daten werden gespeichert, bis sie Session beendet wird, also der Browsertab geschlossen wird
## Speichern
```javascript
sessionStorage.<key> = <value>
sessionStorage.setItem(<key>, <value>)
```
## Lesen
```javascript
let value = sessionStorage.<key>
```
## Löschen
```javascript
sessionStorage.removeItem(<key>)
```