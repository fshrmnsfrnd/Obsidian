---
tags:
Fach:
Thema:
  - "[[HTML]]"
  - "[[Webentwicklung]]"
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
<p>Das ist ein Absatz.</p>
```html
<p>Das ist ein Absatz.</p>
```
## Zeilenumbruch
Text<br>Neue Zeile
```html
Text<br>Neue Zeile
```
## Fett & Kursiv
<strong>Fett</strong>
<em>Kursiv</em>
```html
<strong>Fett</strong>
<em>Kursiv</em>
```
## Zitat
<blockquote>
  Das ist ein Zitat.
</blockquote>
```html
<blockquote>
  Das ist ein Zitat.
</blockquote>
```
## Kurzes Zitat
<q>Zitat</q>
```html
<q>Zitat</q>
```
## Horizontale Linie
<hr>
```html
<hr>
```
## Hochgestellt
x<sup>2</sup>
```html
x<sup>2</sup>
```
## Tiefgestellt
H<sub>2</sub>O
```html
H<sub>2</sub>O
```
## Markierung
<mark>Wichtig</mark>
```html
<mark>Wichtig</mark>
```
## Kleine Schrift
<small>Kleiner Text</small>
```html
<small>Kleiner Text</small>
```
# Listen
## Unsortierte Liste
<ul>
	<li>Apfel</li>
	<li>Banane</li>
</ul>
```html
<ul>
	<li>Apfel</li>
	<li>Banane</li>
</ul>
```
## Sortierte (nummerierte) Liste
<ol>
	<li>Erster</li>
	<li>Zweiter</li>
</ol>
```html
<ol>
	<li>Erster</li>
	<li>Zweiter</li>
</ol>
```
## Beschreibungsliste
<dl>
	<dt>HTML</dt>
	<dd>Auszeichnungssprache</dd>
</dl>
```html
<dl>
	<dt>HTML</dt>
	<dd>Auszeichnungssprache</dd>
</dl>
```
# Tabelle
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
<form>
  <input type="text">
</form>
```html
<form>
  <input type="text">
</form>
```
## Label
<label>Name:</label>
<input type="text">
```html
<label>Name:</label>
<input type="text">
```
## Textarea
<textarea></textarea>
```html
<textarea></textarea>
```
## Button
<button>Klick mich</button>
```html
<button>Klick mich</button>
```
# Input-Typen
## Text
<input type="text">
```html
<input type="text">
```
## Passwort
<input type="password">
```html
<input type="password">
```
## E-Mail
<input type="email">
```html
<input type="email">
```
## Zahl (Spinner)
<input type="number">
```html
<input type="number">
```
## Datum
<input type="date">
```html
<input type="date">
```
## Zeit
<input type="time">
```html
<input type="time">
```
## Farbe
<input type="color">
```html
<input type="color">
```
## Datei
<input type="file">
```html
<input type="file">
```
## Suche
<input type="search">
```html
<input type="search">
```
## URL
<input type="url">
```html
<input type="url">
```
## Telefon
<input type="tel">
```html
<input type="tel">
```
## Verstecktes Feld
<input type="hidden" value="123">
```html
<input type="hidden" value="123">
```
## Senden
<input type="submit" value="Senden">
```html
<input type="submit" value="Senden">
```
## Zurücksetzen
<input type="reset">
```html
<input type="reset">
```
## Checkbox
<input type="checkbox"> AGB akzeptieren
```html
<input type="checkbox"> AGB akzeptieren
```
## Radiobuttons
<input type="radio" name="farbe"> Rot
<input type="radio" name="farbe"> Blau
```html
<input type="radio" name="farbe"> Rot
<input type="radio" name="farbe"> Blau
```
# Dropdown-Menüs
## Einfaches Dropdown
<select>
	<option>Option 1</option>
	<option>Option 2</option>
</select>
```html
<select>
	<option>Option 1</option>
	<option>Option 2</option>
</select>
```
## Gruppierte Optionen
<select>
	<optgroup label="Obst">
		<option>Apfel</option>
		<option>Birne</option>
	</optgroup>
</select>
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
<input type="range" min="0" max="100">
```html
<input type="range" min="0" max="100">
```
## Progress-Bar
<progress value="70" max="100"></progress>
```html
<progress value="70" max="100"></progress>
```
## Meter
<meter value="0.7">70%</meter>
```html
<meter value="0.7">70%</meter>
```
## Output
<output>50</output>
```html
<output>50</output>
```
# Ausklappbare Inhalte
## Details / Summary
<details>
	<summary>Mehr anzeigen</summary>
	Versteckter Text
</details>
```html
<details>
	<summary>Mehr anzeigen</summary>
	Versteckter Text
</details>
```
# Dialog
<dialog open>
	Hallo Welt
</dialog>
```html
<dialog open>
	Hallo Welt
</dialog>
```
# Code
## Inline-Code
<code>let x = 5;</code>
```html
<code>let x = 5;</code>
```
## Codeblock
<pre>
	<code>
		let x = 5;
	</code>
</pre>
```html
<pre>
	<code>
		let x = 5;
	</code>
</pre>
```
# Semantische Layout-Tags
## Header
<header>Kopfbereich</header>
```html
<header>Kopfbereich</header>
```
## Navigation
<nav>Menü</nav>
```html
<nav>Menü</nav>
```
## Main
<main>Inhalt</main>
```html
<main>Inhalt</main>
```
## Section
<section>Abschnitt</section>
```html
<section>Abschnitt</section>
```
## Article
<article>Artikel</article>
```html
<article>Artikel</article>
```
## Aside
<aside>Sidebar</aside>
```html
<aside>Sidebar</aside>
```
## Footer
<footer>Fußbereich</footer>
```html
<footer>Fußbereich</footer>
```
# Medien
## Audio
<audio controls>
	<source src="music.mp3">
</audio>
```html
<audio controls>
	<source src="music.mp3">
</audio>
```
## Video
<video controls width="300">
	<source src="video.mp4">
</video>
```html
<video controls width="300">
	<source src="video.mp4">
</video>
```
# Datum & Zeit
<time datetime="2026-06-03">
	03.06.2026
</time>
```html
<time datetime="2026-06-03">
	03.06.2026
</time>
```
# Fieldset
<fieldset>
	<legend>Persönliche Daten</legend>
	<input type="text">
</fieldset>
```html
<fieldset>
	<legend>Persönliche Daten</legend>
	<input type="text">
</fieldset>
```