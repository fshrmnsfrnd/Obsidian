# CLAUDE.md – Regeln für dieses Obsidian-Vault

Dieses Vault enthält Nicos persönliche Notizen (Technikerschule, Wissenssammlung, Rezepte, Feuerwehr, Homelab). Sprache: **Deutsch**. Teile davon werden mit Quartz veröffentlicht (siehe `index.md`).
## Ordnerstruktur

| Ordner | Inhalt |
| ------ | ------ |
| `Schule/` | Mitschriften der Technikerschule, gegliedert nach Fach: `BA` (Betriebssysteme/Admin), `Programmieren` (Java, Python, C++), `Databases`, `Webentwicklung` (HTML, CSS, JS, PHP) |
| `Knowledge Base/` | Allgemeine Wissenssammlung: Netzwerktechnik, IT Security, KI/Sklearn, Elektrotechnik, Linux, Android, Mathe, Logische Schaltungen, Berufsschule, Wirtschaft und Recht |
| `Kochbuch/` | Rezepte in `Kochen/` und `Cocktails/`, eine Datei pro Rezept |
| `Feuerwehr/` | Orga-Notizen (Jugend, BF Tag, IT) |
| `HomeNet/` | Homelab/Server-Doku (FritzBox, Raspberrys) |
| `Motorrad/` | Wartungslog, Touren, Handbücher |
| `Themen/` | **Leere** Stub-Dateien, die nur als Linkziele für `Thema:`-Links dienen (z.B. `Storage.md`, `UML.md`) |
| `src/` | Alle Anhänge: Bilder (`Pasted image YYYYMMDDHHMMSS.png`), PDFs, Excalidraw-Zeichnungen |
| `src/templates/` | Vorlagen (`Cocktail.md`, `Einsatz.md`, `color.md`) |
| `copilot/` | Plugin-Daten – **nicht anfassen** |
Regeln zur Ablage:
- Neue Notizen thematisch in den passenden Unterordner legen; pro Thema ein Unterordner (z.B. `Knowledge Base/Netzwerktechnik/Protokolle/TCP.md`).
- Eine Notiz = ein Konzept. Der Dateiname ist der Titel (deutsch, normale Groß-/Kleinschreibung, Leerzeichen erlaubt, kein H1 als Titel in der Datei).
- Manche Ordner haben eine gleichnamige Index-Notiz (z.B. `Schule/BA/BA.md`, `Kochbuch/Kochen.md`). Diese sind oft fast leer und dienen als Linkziel für `Thema:`-Links. Beim Anlegen neuer Themenbereiche genauso machen.
- Bilder und Zeichnungen immer in `src/` ablegen und per `![[Dateiname]]` einbetten.
## Frontmatter (Properties)

Jede Wissens-Notiz beginnt mit YAML-Frontmatter. Links darin als zitierte Wikilinks:

```yaml
---
Thema:
  - "[[Java]]"
  - "[[Programmieren]]"
---
```

- `Thema:` Liste von Wikilinks auf die Themen-/Index-Notiz (z.B. `[[Linux]]`, `[[Networks]]`, `[[Java]]`, `[[Security]]`, `[[KI]]`, `[[Kochen]]`, `[[Cocktails]]`). Existierende Themen wiederverwenden, nicht neu erfinden.
- `Kategorie:` nur bei Rezepten, Liste einfacher Strings (z.B. `Longdrinks`, `Shortdrinks`, `Teig`, `Backen`, `Sweet`, `Einfach`, `Nudeln`, `Asiatisch`, `Italienisch`, `Mealprepping`).
## Aufbau einer Notiz
1. Frontmatter.
2. Optional direkt danach ein Blockquote als Kurzdefinition: `>**R**ole **B**ased **A**ccess **C**ontrol` oder `>Beschreibung des Themas`.
3. Inhalt gegliedert mit `#` als oberster Abschnittsebene (H1 = Abschnitt, nicht Titel!), darunter `##`/`###`.
4. Keine Leerzeilen vor/nach Überschriften
5. Nach Haupt-Überschriften folgt eine horizontale Linie `---` in der nächsten Zeile:

```markdown
# Zutaten
---
```
## Schreibstil
- Deutsch, knapp, sachlich, lernorientiert. Keine Füllsätze, keine Einleitungen wie "In dieser Notiz...".
- Stichpunkte, nummerierte Schritte und Tabellen bevorzugen statt langer Fließtexte. Kurze Erklärsätze sind okay.
- Abkürzungen beim ersten Auftreten ausschreiben mit fett markierten Anfangsbuchstaben: `**TCP** steht für **T**ransmission **C**ontrol **P**rotocol`.
- Wichtiges **fett** oder ==hervorgehoben==, Schlussfolgerungen gern mit `->` oder `=>`.
- Befehle und Code immer als `Inline-Code` bzw. Codeblock mit Sprachangabe (```java, ```bash, ...).
- Mathe als LaTeX: inline `$t_ü$`, abgesetzt `$$...$$`.
## Obsidian-Funktionen (aktiv nutzen)
- **Wikilinks**: `[[Notiz]]` oder `[[Pfad/Notiz|Alias]]` zu verwandten Notizen, auch mitten im Satz.
- **Callouts** für Hinweise, häufig genutzt:

```markdown
> [!NOTE] Titel
> Inhalt

> [!WARNING] Achtung
> Inhalt
```

  Verfügbar u.a. `NOTE`, `INFO`, `TIP`, `WARNING`, `IMPORTANT`, `EXAMPLE`, `SUMMARY`. Mit `+`/`-` auf-/zuklappbar. Vollständige Referenz: [[Markdown Beispiel]] im Root.
- **Tabellen** für Vergleiche, Zuordnungen, Portlisten usw.
- **Einbettungen**: `![[Pasted image ....png]]`, `![[Name.excalidraw]]` (Excalidraw liegt auch in `src/`).
- **Tasks**: `- [ ]` Checkboxen
- Mermaid-Diagramme und `%%Kommentare%%` sind möglich.
## Rezepte (festes Schema)
Vorlage `src/templates/Cocktail.md` verwenden.

Cocktails: `Thema: [[Cocktails]]` (ggf. zusätzlich `[[Kochen]]`), Kategorie z.B. `Longdrinks`/`Shortdrinks`/`Spritz`. Mengen mit Einheit in der Menge-Spalte (`2 EL`, `etwas`, `0,5`).
## Was vermeiden
- Keine H1 als Dokumenttitel, keine Emojis.
- Keine neuen Top-Level-Ordner oder Frontmatter-Schlüssel ohne Anlass.
- Anhänge nicht außerhalb von `src/` ablegen.
- `Themen/`-Stubs nicht mit Inhalt füllen, `copilot/` und `.obsidian/` nicht verändern.
