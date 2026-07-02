---
Thema:
  - "[[JavaScript]]"
  - "[[Webentwicklung]]"
---
# While Loop
---
```javascript
while (condition) {
  // code block to be executed
}

let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
```
# Do…While Loop
---
```javascript
x = 0;
i = 0;

do {
  x = x + i;
  console.log(x);
  i++;
} while (i < 5);
```
# For Loop
---
```javascript
for (let i = 0; i < 4; i += 1) {
  console.log(i);
}
```
# Break
---
>The Loop breaks immediately
```javascript
for (let i = 0; i < 99; i += 1) {
  if (i > 5) {
    break;
  }
  console.log(i);
}
```
# Continue
---
>The Loop continues with the next iteration
```javascript
for (i = 0; i < 10; i++) {
  if (i === 3) {
    continue;
  }
  text += 'The number is ' + i + '<br>';
}
```
# Looping Through Arrays
---
```javascript
for (let i = 0; i < array.length; i++) {
  console.log(array[i]);
}
```
# for...in Loop
---
```javascript
const fruits = ['apple', 'orange', 'banana'];

// 1. Print only indexes
for (let index in fruits) {
  console.log(index);
}

// 2. Print only values
for (let index in fruits) {
  console.log(fruits[index]);
}

// 3. Print index with value
for (let index in fruits) {
  console.log(index, fruits[index]);
}
```
# for...of loop
---
```javascript
const fruits = ['apple', 'orange', 'banana'];

for (let [index, value] of fruits.entries()) {
  console.log(index, value);
}
// => 0 apple
// => 1 orange
// => 2 banana
```
