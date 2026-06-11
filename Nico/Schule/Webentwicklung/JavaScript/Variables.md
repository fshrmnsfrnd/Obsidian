---
tags:
Thema:
  - "[[JavaScript]]"
  - "[[Webentwicklung]]"
---
# Scope
---
```javascript
function myFunction() {
  var pizzaName = 'Margarita';
  // Code here can use pizzaName
}

// Code here can't use pizzaName
```
# Block Scoped Variables
---
```javascript
if (true) {
  const statusMessage = 'Logged in.';
}
// Uncaught ReferenceError...
console.log(statusMessage);
```
# Global Variables
---
```javascript
// Variable declared globally
const color = 'blue';

function printColor() {
  console.log(color);
}

printColor(); // => blue
```
# let vs var
---
>`var` is scoped to the nearest function block, and `let` is scoped to the nearest enclosing block.
## let
```javascript
for (let i = 0; i < 3; i++) {
  // This is the Max Scope for 'let'
  // i accessible ✔️
}
// i not accessible ❌
```
## var
```javascript
for (var i = 0; i < 3; i++) {
  var y = i// i accessible ✔️
}
// i accessible ✔️
console.log(i, y)
```

# Gesamtübersicht
---
```javascript
const globalConst = "globalConst"
var globalVar = "globalVar"
let globalLet = "globalLet"
console.log(globalConst, globalVar, globalLet)
//✔️, ✔️, ✔️

if(true){
	console.log(globalConst, globalVar, globalLet)
	//✔️, ✔️, ✔️
	const ifConst = "ifConst"
	var ifVar = "ifVar"
	let ifLet = "ifLet"
	console.log(ifConst, ifVar, ifLet)
	//✔️, ✔️, ✔️
}
console.log(ifConst, ifVar, ifLet)
//❌, ✔️, ❌
```
