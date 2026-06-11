---
Fach: "[[BA]]"
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

|Ausdruck | Beschreibung |
|--- | --- |
|`^` | Zeilen-/Stringanfang |
|`$` | Zeilen-/Stringende |
|`\b` | Wortgrenze (whole-word searches). Beispiel: `\babc\b` |
|`\B` | keine Wortgrenze |
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
# Eigene Zeichenklassen / Beispiele
---

|Ausdruck | Beschreibung |
|--- | --- |
|`[0-7]` | Ziffern 0 bis 7 (Oktalbereich) |
|`[+123]` | `+` oder `1` oder `2` oder `3` (`+` ist hier kein Metazeichen) |
|`[0-9,a-f,A-F]` | Hexadezimalziffern |
|`[^\d]` | Alle Zeichen außer Ziffern (wie `\D`) |
|`\s[^e]+\s` | Wörter ohne `e` (Whitespace, dann mindestens 1 Zeichen ≠ `e`, dann Whitespace) |

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

|Ausdruck | Kurz |
|--- | --- |
|`(a|b)` | Capture von `a` oder `b` |
|`(?:a|b)` | Nicht-capturing Gruppe |
|`(pattern){n}` | Wiederholung einer Gruppe |
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