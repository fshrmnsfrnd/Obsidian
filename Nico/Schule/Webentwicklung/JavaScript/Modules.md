---
tags:
Thema:
  - "[[JavaScript]]"
  - "[[Webentwicklung]]"
---
>Strukturierung von Code in getrennte Dateien
>Ermöglicht sauberen Import und Export von Funktionen, Klassen oder Variablen.
# Export
---
- Definiert, welche Funktionen aus einer Datei nach außen sichtbar sind.
- `default export`: Es gibt genau einen Standard-Export, der ohne geschweifte Klammern importiert wird.
- Benannte Exporte (`export function …`, `export { … }`): Mehrere explizit benannte Funktionen werden exportiert.
- Zweck: Wiederverwendbarer, klar strukturierter Code für Browser und moderne JavaScript-Umgebungen.

```javascript
// myMath.js
// Default export
export default function add(x, y) {
	return x + y;
}
// Normal export
export function subtract(x, y) {
	return x - y;
}

// Multiple exports
function multiply(x, y) {
	return x * y;
}
function duplicate(x) {
	return x * 2;
}
export { multiply, duplicate };
```
# Import
---
- Bindet exportierte Funktionen aus einer anderen Datei ein.
- Default-Export und benannte Exporte werden kombiniert importiert.
- Der Code nutzt die importierten Funktionen direkt.
- `<script type="module">` aktiviert das ES-Modulsystem im Browser.
```javascript
// main.js
import add, { subtract, multiply, duplicate } from './myMath.js';

console.log(add(6, 2)); // 8
console.log(subtract(6, 2)) // 4
console.log(multiply(6, 2)); // 12
console.log(duplicate(5)) // 10

// index.html
<script type="module" src="main.js"></script>
```
# Export Module
---
- Stellt Funktionen über `module.exports` bereit.
- Mehrere Funktionen werden als Objekt exportiert.
- Zweck: Modulsystem für Node.js (klassisch, vor ES Modules).
```javascript
// myMath.js

function add(x, y) {
  return x + y;
}
function subtract(x, y) {
  return x - y;
}


// Multiple exports in [[node.js]]
module.exports = {
  add,
  subtract,
};
```
# Require Module
---
- Lädt ein exportiertes Modul mit `require`.
- Das importierte Modul ist ein Objekt mit den exportierten Funktionen.
- Zugriff erfolgt über Eigenschaften wie `myMath.add`.
```javascript
// main.js
const myMath = require('./myMath.js');

console.log(myMath.add(6, 2)); // 8
```
