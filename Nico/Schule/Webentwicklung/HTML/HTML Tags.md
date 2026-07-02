---
Thema:
  - "[[HTML]]"
  - "[[Webentwicklung]]"
---
## Anfangstag
``` <tagname attribut1="wert1" ... >```
## Endtag
```</tagname>```
## Selbstschließend
```<br />``` 
# Kommentar
```<!--- Kommentar (auch mehrzeilig)-->```
# Head

| Element      | Beschreibung                                                                 |
|--------------|-------------------------------------------------------------------------------|
| !DOCTYPE     | Kein HTML-Element im strengen Sinne, sondern die Information für die Browser, um welche HTML-Version es sich bei der aktuellen Webseite handelt. |
| html         | Kennzeichnet das Dokument als HTML-Dokument                                  |
| head         | Informationen, die nicht im Browserfenster dargestellt werden               |
| title        | Seitentitel, erscheint im Navigationsfeld der Browser und wird im Index der Suchmaschinen übernommen |
| base         | Basis-URL einer Webseite                                                    |
| link         | Erzeugt einen Link zwischen dem aktuellen und einem verwandten Dokument, z.B. für eine CSS-Datei |
| meta         | Informationen, die nicht im Browserfenster dargestellt werden               |
| style        | Globale CSS-Stile, die innerhalb des Dokuments gelten                       |
# Inhalt

| Element                | Beschreibung                                                              |
| ---------------------- | ------------------------------------------------------------------------- |
| body                   | Vom Browser darstellbare Inhalte                                          |
| article                | Inhalte, die unabhängig für sich allein stehen können                     |
| section                | Unterteilt den Inhalt in Abschnitte, i.d.R. mit eigenem header und footer |
| nav                    | Haupt-Navigation mit Links zu anderen Seiten der Webseite                 |
| aside                  | Inhalte, die nicht zu den Hauptinhalten einer Seite zählen                |
| h1, h2, h3, h4, h5, h6 | Überschriften                                                             |
| header                 | Einleitung des Dokuments                                                  |
| footer                 | Informationen im Fuß eines Artikels oder Beitrags                         |
| address                | Kontaktinformationen für den Autor bzw. Inhaber der Seite                 |
# Struktur

| Element        | Beschreibung                                                                                 |
|----------------|---------------------------------------------------------------------------------------------|
| main           | Hauptinhalt der Seite oder der Anwendung                                                    |
| div            | Behälter ohne eigene Eigenschaften                                                          |
| p              | Textabsatz                                                                                  |
| hr             | Horizontale Linie                                                                           |
| pre            | Formatierter Text                                                                           |
| blockquote     | Zitat                                                                                       |
| ol             | Geordnete Liste                                                                             |
| ul             | Ungeordnete Liste                                                                           |
| li             | Listenelement                                                                               |
| menu           | Alternative zum ul-Element für eine ungeordnete Liste von Anweisungen (Toolbar oder Werkzeugleiste) |
| dl             | Beginn einer Definitionsliste                                                               |
| dt             | Begriff in einer Definitionsliste                                                           |
| dd             | Erklärung in einer Definitionsliste                                                        |
| figure         | Container für Bilder, Grafiken und Abbildungen                                              |
| figcaption     | Bildunterschrift, Marginale, Erklärungen zum Inhalt des figure-Elements                     |
# Text

| Element                            | Beschreibung                                                                                             |
|------------------------------------|---------------------------------------------------------------------------------------------------------|
| a                                  | Anker oder Hyperlink: Was zwischen öffnendem und schließendem a-Tag sitzt, wird zu einem klickbaren Link |
| em / i / strong / b                | Leichte Betonung, starke Betonung                                                                       |
| small                              | Kleiner Text                                                                                            |
| cite                               | Kurzes Zitat                                                                                            |
| q                                  | Hochkommas / Anführungszeichen                                                                          |
| dfn                                | Definition                                                                                              |
| abbr                               | Abkürzung                                                                                               |
| data                               | Für Inhalte mit maschinenlesbarer Version im value-Attribut des öffnenden data-Tags                     |
| time                               | Datums- und Zeitangabe mit maschinenlesbarer Version im datetime-Attribut                               |
| code                               | Darstellung von Computer-Code                                                                           |
| var                                | Darstellung als Variable in einem Programm                                                             |
| samp                               | Darstellung als Computercode                                                                            |
| kbd                                | Darstellung für Tastatureingaben                                                                        |
| sub / sup                          | Tiefgestellter und hochgestellter Text                                                                  |
| u                                  | Text stylistisch (z.B. als falsche Rechtschreibung) absetzen                                           |
| mark                               | Hebt einen Text gelb hinterlegt hervor                                                                  |
| details                            | Umschließt ein Detail oder Informationen, die der Benutzer einsehen oder verbergen kann – ein Klappmenü |
| ruby / rt / rp / rb / rtc          | Anmerkungen zur Aussprache / Erklärung in asiatischen Texten                                           |
| bdi                                | Laufrichtung der Schrift innerhalb eines Absatzes                                                      |
| bdo                                | Laufrichtung der Schrift                                                                                |
| span                               | Generischer Behälter für Inline-Inhalte                                                                 |
| br                                 | Neue Zeile                                                                                             |
| wbr                                | Zeilenumbruch möglich                                                                                  |
| del                                | Darstellung als gelöschter Text                                                                         |
| ins                                | Darstellung als eingefügter Text                                                                        |
| s                                  | Nachfolger des veralteten strike-Elements. Heute mit der Bedeutung: nicht länger relevant oder gültig   |
# Medien

| Element    | Beschreibung                                                                         |
|------------|-------------------------------------------------------------------------------------|
| img        | Bild                                                                                |
| picture    | Alternative Bildformate                                                            |
| source     | Verweis auf die Mediendateien eines video- bzw. audio-Elements                      |
| iframe     | Fenster in ein anderes Dokument                                                    |
| embed      | Einbetten von nicht-HTML-Inhalten über Plugins                                      |
| object     | Spielt extern gespeicherte Medien in die Webseite                                  |
| param      | Steueranweisungen für extern gespeicherte Medien                                   |
| video      | Bettet Video in eine Webseite ein                                                  |
| audio      | Bettet Audio in eine Webseite ein                                                  |
| track      | Externe Spuren z.B. Untertitel für Video und Audio, Transkriptionen und Übersetzungen |
| area / map | Bereiche einer Imagemap                                                            |
| svg        | Bettet SVG-Grafik in HTML-Dokumente ein                                            |
| math       | Bettet Formeln in HTML-Dokumente ein                                               |
# Tabellen

| Element   | Beschreibung                |
|-----------|-----------------------------|
| table     | Tabelle                     |
| caption   | Kurzbeschreibung einer Tabelle |
| col       | Tabellenspalte              |
| colgroup  | Tabellenspaltengruppe       |
| tbody     | Körper einer Tabelle        |
| thead     | Tabellenkopf                |
| tfoot     | Tabellenfuß                 |
| td        | Tabellenzelle               |
| th        | Kopfzelle einer Tabelle     |
| tr        | Tabellenreihe               |
# Formulare

| Element     | Beschreibung                                                     |
|-------------|-----------------------------------------------------------------|
| form        | Behälter für ein Formular                                       |
| fieldset    | Behälter für Formularinhalte                                    |
| label       | Beschriftung eines Formularelements                            |
| legend      | Beschriftung eines Formularbereichs                            |
| input       | Eingabefeld                                                    |
| datalist    | Eingabefeld                                                    |
| button      | Schaltfläche                                                   |
| select      | Behälter für eine Auswahlliste                                 |
| option      | Option einer Auswahlliste                                      |
| optgroup    | Optionsgruppe in einer Auswahlliste                            |
| textarea    | Eingabefeld für lange Texte                                    |
| output      | Ausgabe einer Berechnung, die durch ein Script erzeugt wurde (z.B. aktueller Wert des range-Sliders) |
| progress    | Fortschrittsbalken                                             |
| meter       | Wert innerhalb eines bestimmten Bereichs                       |
# Skripte

| Element   | Beschreibung                                                                 |
|-----------|-----------------------------------------------------------------------------|
| script    | Aufruf eines Scripts                                                       |
| noscript  | Alternativer Inhalt für Browser ohne Scriptunterstützung                   |
| canvas    | Erzeugt eine Zeichenfläche, die von JavaScript mit Bildern gefüllt wird    |
| template  | Für JavaScript gedacht; fügt Struktur und Inhalt dynamisch ein             |
# Interaktiv

| Element   | Beschreibung                                                                 |
|-----------|-----------------------------------------------------------------------------|
| details   | Zusätzliche Informationen, die der Benutzer sehen und verbergen kann        |
| summary   | Klickbare Überschrift für details                                           |
| dialog    | Öffnet ein Overlay oder modales Fenster                                      |
