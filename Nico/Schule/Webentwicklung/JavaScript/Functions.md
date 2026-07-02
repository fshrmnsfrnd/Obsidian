---
Thema:
  - "[[JavaScript]]"
  - "[[Webentwicklung]]"
---
# Functions
---
```javascript
// Defining the function:
function sum(num1, num2) {
  return num1 + num2;
}

// Calling the function:
console.log(sum(3, 6)); // 9

```
# Anonymous Functions
---
```javascript
let greet = function() {
  console.log("Hello!");
};

const greetMe = function(name) {
  console.log("Hello ", name);
};
greet();
greetMe("Nico")
```
# Arrow Functions
---
## With no arguments
```javascript
const printHello = () => {
	console.log('hello');
};
printHello(); // => hello
```
## With arguments
```javascript
const sum = (param1, param2) => {
	return param1 + param2;
};
console.log(sum(2, 5)); // => 7
```
## Concise arrow functions
```javascript
const multiply = (a, b) => a * b;
console.log(multiply(2, 30)); // => 60
```
# return Keyword
---
```javascript
// With return
function sum(num1, num2) {
  return num1 + num2;
}

// The function doesn't output the sum
function sum(num1, num2) {
  num1 + num2;
}
```
## Functions Assigned to [[Variables]]
---
```javascript
let plusFive = (number) => {
  return number + 5;
};
let f = plusFive; // f is assigned the value of plusFive
plusFive(3); // 8
// Since f has a function value, it can be invoked.
f(5); // 10
```
## Callback Functions
---
```javascript
const isEven = (n) => {
  return n % 2 == 0;
};

let printMsg = (evenFunc, num) => {
  const isNumEven = evenFunc(num);
  console.log(`${num} is an even number: ${isNumEven}.`);
};

// Pass in isEven as the callback function
printMsg(isEven, 4);
// => 4 is an even number: True.
```
# Restparameter
---
>Wenn `...<name>` angegeben ist, werden alle weiteren Parameter in dieses Array gespeichert
```javascript
function func(param1, ...paramN){
	for(var i = 0; i < paramN.length; i++){
		let param = paramN[i]
	}
}
```