---
Thema:
---

>**Regular Expressions (Regex)** sind mächtige Werkzeuge für Mustersuche und Textverarbeitung. Dieser Spickzettel bietet eine umfassende Übersicht mit praktischen Beispielen.

# Grundlagen der Regex-Syntax
---
## Literale Zeichen
- `abc` – findet exakt "abc"
- `123` – findet exakt "123"
- Buchstaben und Zahlen werden wörtlich interpretiert
## Metazeichen (müssen escaped werden)
Diese Zeichen haben spezielle Bedeutungen und müssen mit `\` escaped werden, wenn sie wörtlich gemeint sind:
``. ^ $ * + ? { } [ ] \ | ( )``

**Beispiele:**  
`\.` findet einen Punkt  
`\$` findet ein Dollar-Zeichen  
`$` findet eine öffnende Klammer
# Quantifier (Wiederholungen)
---

|Quantifier|Bedeutung|Beispiel|Findet|
|---|---|---|---|
|`*`|0 oder mehr|`a*`|"", "a", "aa", "aaa"|
|`+`|1 oder mehr|`a+`|"a", "aa", "aaa"|
|`?`|0 oder 1 (optional)|`colou?r`|"color", "colour"|
|`{n}`|exakt n mal|`\d{3}`|"123", "456"|
|`{n,}`|mindestens n mal|`\d{2,}`|"12", "123", "1234"|
|`{n,m}`|zwischen n und m|`\d{2,4}`|"12", "123", "1234"|
## Gierig vs. Nicht-gierig

### Gierig (greedy)
`.*` – matcht so viel wie möglich  
Text: "a123b456c"  
`a.*c` findet: "a123b456c"
### Nicht-gierig (lazy)
`.*?` – matcht so wenig wie möglich  
Text: "a123b456c"  
`a.*?c` findet: "a123b456c" (minimal)

# Zeichenklassen
---
## Vordefinierte Klassen

|Klasse|Bedeutung|Gegenteil|Beispiel|
|---|---|---|---|
|`\d`|Ziffer (0-9)|`\D` (keine Ziffer)|`\d+` findet "123"|
|`\w`|Wortzeichen (a-z, A-Z, 0-9, _)|`\W`|`\w+` findet "hello_123"|
|`\s`|Whitespace (Leerzeichen, Tab, Newline)|`\S`|`\s+` findet Leerzeichen|
|`.`|Beliebiges Zeichen (außer Newline)|-|`a.c` findet "abc", "a1c"|
## Eigene Zeichenklassen

|Pattern|Beschreibung|Beispiel|
|---|---|---|
|`[abc]`|Eines der Zeichen a, b oder c|`[aeiou]` findet Vokale|
|`[a-z]`|Alle Kleinbuchstaben|`[a-z]+` findet "hello"|
|`[A-Z]`|Alle Großbuchstaben|`[A-Z]+` findet "HELLO"|
|`[0-9]`|Alle Ziffern|`[0-9]{3}` findet "123"|
|`[^abc]`|NICHT a, b oder c (Negation)|`[^0-9]` findet Nicht-Ziffern|
|`[a-zA-Z0-9]`|Alphanumerisch|`[a-zA-Z0-9]+` findet "Test123"|
# Positionsanker
---

|Anker|Bedeutung|Beispiel|Findet / Findet nicht|
|---|---|---|---|
|`^`|Zeilenanfang|`^Start`|✅ "Start hier" / ❌ "Der Start"|
|`$`|Zeilenende|`Ende$`|✅ "Das Ende" / ❌ "Ende ist nah"|
|`\b`|Wortgrenze|`\bwort\b`|✅ "ein wort hier" / ❌ "worte"|
|`\B`|Keine Wortgrenze|`\Bwort`|✅ "Unwort" / ❌ "wort"|

>[!TIPP] 
>Verwenden Sie `^` und `$` zusammen, um exakte Übereinstimmungen zu erzwingen:  
`^\d{5}$` findet nur Strings, die exakt aus 5 Ziffern bestehen.
# Gruppen und Alternativen
---
## Gruppen

|Syntax|Typ|Beschreibung|Beispiel|
|---|---|---|---|
|`(abc)`|Erfassungsgruppe|Wird gespeichert und kann referenziert werden|`(\d{3})-(\d{2})`|
|`(?:abc)`|Nicht-erfassend|Nur Gruppierung, kein Speichern|`(?:http\|https)://`|
|`(a\|b)`|Alternative|a ODER b|`(jpg\|png\|gif)`|
## Rückverweise

**Beispiel 1:** Doppelte Wörter finden  
`(\w+)\s+\1` findet "das das" oder "test test"  
  
**Beispiel 2:** Wiederholte Zeichen  
`(abc)\1` findet "abcabc"
## Lookahead und Lookbehind

|Syntax|Name|Beschreibung|Beispiel|
|---|---|---|---|
|`(?=...)`|Positive Lookahead|Muss folgen, wird nicht erfasst|`\d(?=€)` findet Ziffern vor €|
|`(?!...)`|Negative Lookahead|Darf nicht folgen|`\d(?!€)` findet Ziffern NICHT vor €|
|`(?<=...)`|Positive Lookbehind|Muss vorangehen|`(?<=€)\d` findet Ziffern nach €|
|`(?<!...)`|Negative Lookbehind|Darf nicht vorangehen|`(?<!€)\d` findet Ziffern NICHT nach €|
# Praktische Regex-Patterns
---
## Zahl in Text
`zahl = str.match(/\d+/g)`
## Email-Adresse (einfach)
`^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$`
**Erklärt:**
- `[a-zA-Z0-9._%+-]+` – Benutzername (Buchstaben, Zahlen, Sonderzeichen)
- `@` – At-Zeichen (Pflicht)
- `[a-zA-Z0-9.-]+` – Domain-Name
- `\.[a-zA-Z]{2,}` – Top-Level-Domain (mindestens 2 Zeichen)
## URL (HTTP/HTTPS)
``^https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)$``
## Datum (DD.MM.YYYY oder DD/MM/YYYY)
``^(0[1-9]|[12][0-9]|3[01])[./-](0[1-9]|1[012])[./-](19|20)\d\d$``
**Findet:** 01.01.2024, 31/12/2023, 15-06-1999
## Telefonnummer (deutsch)
``^(\+49|0)[1-9]\d{1,14}$``
**Findet:** +4915112345678, 015112345678
## Deutsche Postleitzahl
``^\d{5}$``
**Findet:** 10115, 80331, 20095
## IP-Adresse (IPv4)
``^((25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$``
**Findet:** 192.168.1.1, 10.0.0.1, 255.255.255.0
## Passwort-Validierung
``^(?=.*[A-Z])(?=.*[a-z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$``
**Anforderungen:**
- Mindestens 8 Zeichen
- Mindestens 1 Großbuchstabe
- Mindestens 1 Kleinbuchstabe
- Mindestens 1 Ziffer
- Mindestens 1 Sonderzeichen
## UUID
``^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$``
**Findet:** 550e8400-e29b-41d4-a716-446655440000
## HTML-Tags entfernen
``<[^>]*>``
**Beispiel:** 
``<p>Text</p>`` → "Text"
## Hexadezimal-Farbcode
``^#?([a-fA-F0-9]{6}|[a-fA-F0-9]{3})$``
**Findet:** "#FF5733", "#F00", "FF5733"
## Kreditkartennummer (Visa/Mastercard)
``^(?:4[0-9]{12}(?:[0-9]{3})?|5[1-5][0-9]{14})$``
## MAC-Adresse
``^([0-9A-Fa-f]{2}[:-]){5}([0-9A-Fa-f]{2})$``
**Findet:** 00:1B:44:11:3A:B7, 00-1B-44-11-3A-B7
# Performance-Tipps
---
### 1. Backtracking vermeiden
❌ `(a+)+b` – kann extrem langsam werden  
✅ `a+b` – effizienter
### 2. Anker verwenden
`^` und `$` begrenzen die Suche und verbessern die Performance erheblich
### 3. Spezifische Zeichenklassen
✅ `[0-9]` ist klarer als `\d`  
✅ `[a-z]` statt `\w` wenn möglich
### 4. Nicht-erfassende Gruppen
✅ `(?:...)` statt `(...)`  
wenn kein Rückverweis nötig ist
### 5. Gierige Quantifier bevorzugen
`.*` ist oft schneller als `.*?`  
(wenn das Ergebnis gleich ist)
### 6. Alternativen optimieren
✅ `(?:jpg|png|gif)`  
Längere Alternativen zuerst: `(jpeg|jpg)`

> [!Warning] 
> Verschachtelte Quantifier wie `(a*)*` oder `(a+)+` können zu exponentieller Laufzeit führen (ReDoS - Regular Expression Denial of Service).
# MongoDB Regex-Beispiele
### Suche nach Email-Domains
`db.users.find({ email: { $regex: /@gmail\.com$/, $options: 'i' } })`
### Suche nach Postleitzahlen in Berlin (10xxx - 14xxx)
``db.addresses.find({ plz: { $regex: /^1[0-4]\d{3}$/ } })``
### Case-insensitive Suche
``db.products.find({ name: { $regex: /laptop/i } })``
### MongoDB Regex-Optionen

|Option|Bedeutung|Beispiel|
|---|---|---|
|`i`|Case-insensitive|`{ $regex: /test/i }`|
|`m`|Multiline (^ und $ für jede Zeile)|`{ $regex: /^test/m }`|
|`x`|Erweitert (Whitespace ignorieren)|`{ $regex: /t e s t/x }`|
|`s`|Dot-all (. matcht auch Newline)|`{ $regex: /.*/s }`|
# Unterschiede zwischen Sprachen

|Feature|JavaScript|Python|Java|PHP|
|---|---|---|---|---|
|Syntax|`/pattern/flags`|`r"pattern"`|`"pattern"`|`/pattern/flags`|
|Case-insensitive|`/test/i`|`re.IGNORECASE`|`Pattern.CASE_INSENSITIVE`|`/test/i`|
|Multiline|`/test/m`|`re.MULTILINE`|`Pattern.MULTILINE`|`/test/m`|
|Lookbehind|✅ (ES2018+)|✅|✅|✅|
|Named Groups|`(?<name>...)`|`(?P<name>...)`|`(?<name>...)`|`(?P<name>...)`|
# Regex-Flags
---

|Flag|Name|Beschreibung|JavaScript|Python|
|---|---|---|---|---|
|`i`|Case-insensitive|Groß-/Kleinschreibung ignorieren|`/test/i`|`re.I`|
|`g`|Global|Alle Vorkommen finden|`/test/g`|-|
|`m`|Multiline|^ und $ für jede Zeile|`/test/m`|`re.M`|
|`s`|Dotall|. matcht auch Newline|`/test/s`|`re.S`|
|`u`|Unicode|Unicode-Modus|`/test/u`|-|
|`x`|Extended|Whitespace und Kommentare erlauben|-|`re.X`|
# Weitere nützliche Patterns
---
#### IBAN (deutsch)
`^DE\d{20}$`
#### ISBN-10
`^\d{9}[\dX]$`
#### Zeit (HH:MM)
`^([01]\d|2[0-3]):([0-5]\d)$`
#### Logfile-Zeitstempel
`^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}`
#### Dateiname mit Extension
`^[\w\-. ]+\.(jpg|png|pdf)$`
#### Markdown-Link
`$$([^$$]+)$$$([^)]+)$`
# Nützliche Tools zum Testen

- **regex101.com** – Interaktiver Regex-Tester mit Erklärungen
- **regexr.com** – Visueller Regex-Editor
- **regexpal.com** – Einfacher Online-Tester
- **debuggex.com** – Visualisiert Regex als Diagramm
- **regextester.com** – Multi-Language Support

---

**Erweiterte Regex Spickzettel** | Erstellt 2024  
Für Fragen und Feedback: Regex-Community