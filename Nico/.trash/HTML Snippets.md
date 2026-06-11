---
tags:
Fach: "[[INTL]]"
Thema:
  - "[[HTML]]"
---
## Link
<a href="https://example.com">Link</a>
```html
<a href="https://example.com">Link</a>
```
## Bild
<img src="bild.jpg" alt="Bild">
```html
<img src="bild.jpg" alt="Bild">
```
# Text
## Überschriften
<h1>Überschrift 1</h1>
<h2>Überschrift 2</h2>
```html
<h1>Überschrift 1</h1>
<h2>Überschrift 2</h2>
```
## Absatz
```html
<p>Das ist ein Absatz.</p>
```
## Zeilenumbruch
```html
Text<br>Neue Zeile
```
## Fett & Kursiv
```html
<strong>Fett</strong>
<em>Kursiv</em>
```
## Zitat
```html
<blockquote>
  Das ist ein Zitat.
</blockquote>
```
## Kurzes Zitat
```html
<q>Zitat</q>
```
## Horizontale Linie
```html
<hr>
```
## Hochgestellt
```html
x<sup>2</sup>
```
## Tiefgestellt
```html
H<sub>2</sub>O
```
## Markierung
```html
<mark>Wichtig</mark>
```
## Kleine Schrift
```html
<small>Kleiner Text</small>
```
# Listen
## Unsortierte Liste
```html
<ul>
	<li>Apfel</li>
	<li>Banane</li>
</ul>
```
## Sortierte (nummerierte) Liste
```html
<ol>
	<li>Erster</li>
	<li>Zweiter</li>
</ol>
```
## Beschreibungsliste
```html
<dl>
	<dt>HTML</dt>
	<dd>Auszeichnungssprache</dd>
</dl>
```
# Tabelle
```html
<table>
	<tr>
		<th>Name</th>
		<th>Alter</th>
	</tr>
	<tr>
		<td>Max</td>
		<td>25</td>
	</tr>
</table>
```
# Formulare
## Einfaches Formular
```html
<form>
  <input type="text">
</form>
```
## Label
```html
<label>Name:</label>
<input type="text">
```
## Textarea
```html
<textarea></textarea>
```
## Button
```html
<button>Klick mich</button>
```
# Input-Typen
## Text
```html
<input type="text">
```
## Passwort
```html
<input type="password">
```
## E-Mail
```html
<input type="email">
```
## Zahl (Spinner)
```html
<input type="number">
```
## Datum
```html
<input type="date">
```
## Zeit
```html
<input type="time">
```
## Farbe
```html
<input type="color">
```
## Datei
```html
<input type="file">
```
## Suche
```html
<input type="search">
```
## URL
```html
<input type="url">
```
## Telefon
```html
<input type="tel">
```
## Verstecktes Feld
```html
<input type="hidden" value="123">
```
## Senden
```html
<input type="submit" value="Senden">
```
## Zurücksetzen
```html
<input type="reset">
```
## Checkbox
```html
<input type="checkbox"> AGB akzeptieren
```
## Radiobuttons
```html
<input type="radio" name="farbe"> Rot
<input type="radio" name="farbe"> Blau
```
# Dropdown-Menüs
## Einfaches Dropdown
```html
<select>
	<option>Option 1</option>
	<option>Option 2</option>
</select>
```
## Gruppierte Optionen
```html
<select>
	<optgroup label="Obst">
		<option>Apfel</option>
		<option>Birne</option>
	</optgroup>
</select>
```
# Slider & Fortschritt
## Range (Slider)
```html
<input type="range" min="0" max="100">
```
## Progress-Bar
```html
<progress value="70" max="100"></progress>
```
## Meter
```html
<meter value="0.7">70%</meter>
```
## Output
```html
<output>50</output>
```
# Ausklappbare Inhalte
## Details / Summary
```html
<details>
	<summary>Mehr anzeigen</summary>
	Versteckter Text
</details>
```
# Dialog
```html
<dialog open>
	Hallo Welt
</dialog>
```
# Code
## Inline-Code
```html
<code>let x = 5;</code>
```
## Codeblock
```html
<pre>
	<code>
		let x = 5;
	</code>
</pre>
```
# Semantische Layout-Tags
## Header
```html
<header>Kopfbereich</header>
```
## Navigation
```html
<nav>Menü</nav>
```
## Main
```html
<main>Inhalt</main>
```
## Section
```html
<section>Abschnitt</section>
```
## Article
```html
<article>Artikel</article>
```
## Aside
```html
<aside>Sidebar</aside>
```
## Footer
```html
<footer>Fußbereich</footer>
```
# Medien
## Audio
```html
<audio controls>
	<source src="music.mp3">
</audio>
```
## Video
```html
<video controls width="300">
	<source src="video.mp4">
</video>
```
# Datum & Zeit
```html
<time datetime="2026-06-03">
	03.06.2026
</time>
```
# Fieldset
```html
<fieldset>
	<legend>Persönliche Daten</legend>
	<input type="text">
</fieldset>
```