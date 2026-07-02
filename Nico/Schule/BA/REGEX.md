---
Thema:
---
# Metazeichen / Grundzeichen
---

| Ausdruck  | Beschreibung                                                                                     |
| --------- | ------------------------------------------------------------------------------------------------ |
| `.`       | Ein beliebiges Zeichen. Beispiel: `a.c` ⇒ `aac`, `abc`                                           |
| `\.`      | Literal Punkt (suche den Punkt `.`)                                                              |
| `^`       | Zeilen-/Stringanfang. Beispiel: `^abc`                                                           |
| `$`       | Zeilen-/Stringende. Beispiel: `abc$`                                                             |
| `[]`      | Zeichenklasse. Beispiel: `[A-Za-z0-9]`                                                           |
| `[^...]`  | Negierte Zeichenklasse (kein Zeichen aus ...). Beispiel: `[^e]`                                  |
| `-`       | Bereich in Zeichenklasse. Beispiel: `[0-9]`                                                      |
| `()`      | Gruppierung / Capture. Beispiel: `(\d+)`                                                         |
| `(?:...)` | Gruppierung ohne Capture                                                                         |
| `\|`      | Oder (Alternation). Beispiel: `M(a \| e)ier` (ohne \\ geht nur nich anders wegen Markdown Table) |
| `\`       | Escape für Metazeichen, leitet vordefinierte Klassen ein                                         |
# Quantifier
---

|Ausdruck | Beschreibung |
|--- | --- |
|`*` | 0 oder mehr |
|`+` | 1 oder mehr |
|`?` | 0 oder 1 (optional) |
|`{n}` | genau n |
|`{n,m}` | zwischen n und m |
|`{n,}` | mindestens n |
|`.*?` | lazy (falls Flavor unterstützt) |

# Anchors & Wortgrenzen
---

| Ausdruck | Beschreibung                                          |
| -------- | ----------------------------------------------------- |
| `^`      | Zeilen-/Stringanfang                                  |
| `$`      | Zeilen-/Stringende                                    |
| `\b`     | Wortgrenze (whole-word searches). Beispiel: `\babc\b` |
| `\B`     | keine Wortgrenze                                      |
# Lookahead und Lookbehind
---

| Syntax     | Name                | Beschreibung                    | Beispiel                               |
| ---------- | ------------------- | ------------------------------- | -------------------------------------- |
| `(?=...)`  | Positive Lookahead  | Muss folgen, wird nicht erfasst | `\d(?=€)` findet Ziffern vor €         |
| `(?!...)`  | Negative Lookahead  | Darf nicht folgen               | `\d(?!€)` findet Ziffern NICHT vor €   |
| `(?<=...)` | Positive Lookbehind | Muss vorangehen                 | `(?<=€)\d` findet Ziffern nach €       |
| `(?<!...)` | Negative Lookbehind | Darf nicht vorangehen           | `(?<!€)\d` findet Ziffern NICHT nach € |
# Gierig vs. Nicht-gierig
---
## Gierig (greedy)
`.*` – matcht so viel wie möglich  
Text: "a123b456c"  
`a.*c` findet: "a123b456c"
## Nicht-gierig (lazy)
`.*?` – matcht so wenig wie möglich  
Text: "a123b456c"  
`a.*?c` findet: "a123b456c" (minimal)
# Vordefinierte Zeichenklassen
---

|Ausdruck | Bedeutung | Beispiel |
|--- | --- | --- |
|`\s` | Whitespace (Space, Tab, Newline) | `\s+` findet Leerraum |
|`\S` | Kein Whitespace | `\S+` |
|`\d` | Ziffer (0–9) | `\d{4,8}` (z. B. `089 5001`) |
|`\D` | Keine Ziffer | `\D+` |
|`\w` | Word-Character (Buchst., Ziff., `_`) | `\w+` |
|`\W` | Kein Word-Character | `\W+` |
|`\b` | Wortgrenze | siehe oben |
|`\B` | Keine Wortgrenze | siehe oben |

Beispiel aus Text:  
- `a\db` ⇒ passt: `a0b`, `a1b`, ... `a9b`  
- `\d{4,8}` ⇒ z. B. `089 5001` (Münchner Telefonnummer, vereinfacht)
# Eigene Zeichenklassen
---

| Pattern       | Beschreibung                  | Beispiel                        |
| ------------- | ----------------------------- | ------------------------------- |
| `[abc]`       | Eines der Zeichen a, b oder c | `[aeiou]` findet Vokale         |
| `[a-z]`       | Alle Kleinbuchstaben          | `[a-z]+` findet "hello"         |
| `[A-Z]`       | Alle Großbuchstaben           | `[A-Z]+` findet "HELLO"         |
| `[0-9]`       | Alle Ziffern                  | `[0-9]{3}` findet "123"         |
| `[^abc]`      | NICHT a, b oder c (Negation)  | `[^0-9]` findet Nicht-Ziffern   |
| `[a-zA-Z0-9]` | Alphanumerisch                | `[a-zA-Z0-9]+` findet "Test123" |
Hinweis: In Zeichenklassen sind `[]^ -` kontextabhängig normale Zeichen.
# Beispiele für häufige Muster
---

|Ausdruck | Zweck |
|--- | --- |
|`abc` | Enthält `abc` |
|`^abc` | Beginnt mit `abc` |
|`abc$` | Endet mit `abc` |
|`\babc\b` | Ganzes Wort `abc` |
|`^\d+$` | Nur Ziffern (ganzer String) |
|`.+` | Mindestens 1 Zeichen |
|`[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}` | Einfache E‑Mail |
|`\b(?:\d{1,3}\.){3}\d{1,3}\b` | Vereinfachte IPv4 |
|`words?` | `word` oder `words` |
`\d+(,\d+)?` | Zahl mit optionalen Nachkommastellen (Komma) |
# Gruppen / Alternation
---

| Syntax    | Typ              | Beschreibung                                  | Beispiel             |
| --------- | ---------------- | --------------------------------------------- | -------------------- |
| `(abc)`   | Erfassungsgruppe | Wird gespeichert und kann referenziert werden | `(\d{3})-(\d{2})`    |
| `(?:abc)` | Nicht-erfassend  | Nur Gruppierung, kein Speichern               | `(?:http\|https)://` |
| `(a\|b)`  | Alternative      | a ODER b                                      | `(jpg\|png\|gif)`    |
# Tools / Flags (Kurz)
---

| Ausdruck | Bedeutung |
|--- | --- |
|`i` | Case-insensitive (`(?i)pattern` oder Tool‑Flag) |
|`m` | Multiline (`^`/`$` pro Zeile) |
|`s` | Dotall (`.` matcht `\n`) |
|`grep -E` | erweiterte Regex (POSIX‑ERE) |
|`grep -P` | Perl‑like (PCRE) |
|`regex101.com` | Testen: Flavor wählen (PCRE, ECMAScript, POSIX) |
# PowerShell: Operatoren
---

|Operator | Kurzbeschreibung | Beispiel |
|--- | --- | --- |
|`-match` / `-imatch` / `-cmatch` | Prüft Match; `i` = case-insens., `c` = case-sens. | `$eingabe -match ".{8,}"` (>=8 Zeichen) |
|`-notmatch` / `-inotmatch` / `-cnotmatch` | Kein Treffer | |
|`-replace` / `-ireplace` / `-creplace` | Ersetzt (liefert String) | `$old = "Windows 8.0" ; $old -replace "8\.\d","10"` ⇒ `Windows 10` |
|`-split` | Zerlegt String an Pattern (Trennzeichen nicht im Ergebnis) | `$woerter = "a b c" -split "\s"` |

PowerShell-Beispiele (Code):
```powershell
# Match-Beispiel: mindestens 8 Zeichen
if ($eingabe -match ".{8,}") { "OK." } else { "Ungültig." }

# Replace-Beispiel: 8.x -> 10
$old = "Windows 8.1"
$old -replace "8\.\d", "10"   # -> "Windows 10"

# Split-Beispiel: Auftrennen bei Whitespace
$woerter = "Das sind Wörter." -split "\s"
```

Wichtig: Bei -replace mit Backreferences den Ersetzungsstring in `'...'` setzen (keine Variablen-Interpolation), z. B. `'$1Linux$2'`.
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
## IBAN (deutsch)
`^DE\d{20}$`
## ISBN-10
`^\d{9}[\dX]$`
## Zeit (HH:MM)
`^([01]\d|2[0-3]):([0-5]\d)$`
## Logfile-Zeitstempel
`^\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}`
## Dateiname mit Extension
`^[\w\-. ]+\.(jpg|png|pdf)$`
## Markdown-Link
`$$([^$$]+)$$$([^)]+)$`