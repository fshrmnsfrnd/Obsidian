---
Thema:
  - "[[Security]]"
---
Gehört zu [[Authentifikation#Wissen]]

>Der Nutzer gibt seine digitale Identität und das Passwort ein. Das IT-System vergleicht mit den gespeicherten Daten und authentifiziert bei korrekten Daten den Nutzer. Falsche Angaben werden abgelehnt.


> [!NOTE] 
> Die Sicherheit des Passwortverfahrens beruht auf der Qualität und Geheimhaltung der genutzten Passwörter, beim Nutzer, im IT-System und während der Eingabe und Übertragung.

# Mögliche [[Angreifer#Angriffsvektoren (Angriffsmethoden)|Angriffsvektoren]]: 
---
## Erraten des Passworts 
- Erraten des Passworts durch Social Engineering 
- Erraten des Passworts durch Ausprobieren: 
	- Wörterbuchangriff 
	- Brute-Force-Angriff 
## Abfangen von Nutzernamen und Passworts während der Übertragung 
Angreifer versucht das Passwort im Klartext mitzulesen. Das ist überall möglich, wo das Passwort unverschlüsselt übertragen wird. 
## Entwenden der Liste von Nutzernamen und Passwörtern
Der Angreifer entwendet die gespeicherten Nutzerdaten vom IT-System. 
## Sonstige
- Keylogger 
- Phishing 
- Spear Phishing 
- Whaling 
- Über die Schulter schauen 
- Nutzer überreden Passwörter zu verraten (social Enineering) 
- Ein bekanntes Passwort auf einem anderen IT-System ausprobieren. 
- Unsicheres Passwort Reset-Verfahren
# Sicherheitsmechanismen
---
## Passwortregeln und Passwörter überprüfen 
Es wird sicher gestellt, dass die Passwörter nicht zu einfach sind. Die Nutzer werden daran gehindert zu einfache Passwörter zu verwenden 
- Je länger desto besser, min. 13, besser 20
- Sonderzeichen, Zahlen, Großbuchstaben, Kleinbuchstaben
- Zeichenabfolge soll zufällig sein.
- einmalig (Keine Mehrfachverwendung von Passwörtern für verschiedene Accounts)
- sicher speichern
- unzugänglich für andere
## Fehlbedienungszähler
Jede Fehleingabe wird gezählt. Nach einen Anzahl von Fehlversuchen muss eine Pause gemacht werden. 
## Verschlüsselung
Passwörter werden nie unverschlüsselt übertragen. 
## Passwort-Hash Verfahren
Es werden nur die Hash-Werte der Passwörter gespeichert. Für das eingegebene Passwort wird auch ein Hash berechnet. Die beiden Hashwerte werden verglichen.
# Passwörter speichern
---
Unter Linux in `/etc/shadow` (Nur Root lesbar)
Die Passwörter werden gehashed gespeichert. Die Hashes können nicht zurück gerechnet werden.

Linux speichert Passwort-Hashes immer in der Datei /etc/shadow. Sie ist nur für root lesbar. Im Bildschirmfoto oben steht nach dem Benutzernamen $6$ al s Abkürzung für den Hash-Algorithmus SHA-512. Darauf folgen einige Zeichen mit dem Salz und nach dem nächsten Dollar-Zeichen der Passwort-Hash. Das erste Zeichen nach dem Hash ist ein Doppelpunkt.
# Rainbow Tables
---
- Liste mit Passwörtern und deren Hash-Werten (für einen bestimmten Hash-Algorithmus)
- Zum „Nachsehen“, welche Hash-Werte zu welchen Passwörtern gehören. 
# Salt
---
- Vor dem Anwenden der Hash-Funktion wird dem Passwort noch eine Zeichenkette hinzugefügt.
- Bsp. für Zeichenkette: Nutzername
- Speicherort: Auf dem System, auf dem die ge-hashten Passwörter liegen.
# Pepper
---
Wie Salt, nur die dem Passwort hinzugefügte Zeichenkette wird auf einem anderen System gespeichert
# Wordlist
---
- Wörter, die häufig für Passwörter verwendet werden.
- Kann für zu hackende Zielpersonen angepasst werden.
# Wörterbuchattacken
---
- Wörter eines Wörterbuchs werden als Passwort ausprobiert.
# Brute-Force Attacken
---
- Alle Buchstaben-Zahlen-Zeichenkombinationen ausprobieren.
# Social Engineering
---
- Es wird versucht, eine Person zu manipulieren, um Zugang(sdaten) zu erhalten.
# Diceware-Verfahren
---
Man würfelt aus einer Wortliste welche Wörter man als Passwort nimmt. Als Nummern nimmt man nur die Ziffern 1-6 weil nur das der Würfel abbilden kann. so kann man mit 5 Würfen eine Liste von $6⁵=7776$ Wörtern bedienen.