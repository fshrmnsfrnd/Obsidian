---
Thema:
  - "[[JavaScript]]"
  - "[[Webentwicklung]]"
---
# Arrays
---
```javascript
const fruits = ['apple', 'orange', 'banana'];
// Different data types
const data = [1, 'chicken', false];
```
# Property .length
---
```javascript
const numbers = [1, 2, 3, 4];
numbers.length; // 4
```
# Index
---
```javascript
const myArray = [100, 200, 300];
console.log(myArray[1]); // 200
console.log(myArray[-1]); // 300
```
# Mutable chart
---

|           | add | remove | start | end |
| :-------- | :-: | :----: | :---: | :-: |
| `push`    |  ✔  |        |       |  ✔  |
| `pop`     |     |   ✔    |       |  ✔  |
| `unshift` |  ✔  |        |   ✔   |     |
| `shift`   |     |   ✔    |   ✔   |     |

```javascript
// Adding a single element:
const cart = ['apple', 'orange'];
cart.push('pear');

// Adding multiple elements:
const numbers = [1, 2];
numbers.push(3, 4, 5);
//Add items to the end and returns the new array length.

const fruits = ['apple', 'orange', 'banana'];
const fruit = fruits.pop(); // 'banana'
console.log(fruits); // ["apple", "orange"]
//Remove an item from the end and returns the removed item.

let cats = ['Bob', 'Willy', 'Mini'];
cats.shift(); // ['Willy', 'Mini']
//Remove an item from the beginning and returns the removed item.

let cats = ['Willy', 'Bob']; //['Willy', 'Bob']
cats.unshift('Willy'); // ['Bob']
//Add items to the beginning and returns the new array length.
```
# Array.concat()
---
```javascript
const numbers = [3, 2, 1];
const newFirstNumber = 4; // => [ 4, 3, 2, 1 ]
[newFirstNumber].concat(numbers); // => [ 3, 2, 1, 4 ]
numbers.concat(newFirstNumber);
```
If you want to avoid mutating your original array, you can use concat.
# Array.reduce()
---
```javascript
const numbers = [1, 2, 3, 4];

const sum = numbers.reduce((accumulator, curVal) => {
  return accumulator + curVal;
});

console.log(sum); // 10
```
# Array.map()
---
Calls a defined callback function on each element of an array, and returns an array that contains the results.
```javascript
const numbers = [65, 44, 12, 4];  
const newArr = numbers.map((value, index, array) => {return value * 10})
//650,440,120,40
```
# Array.forEach()
---
Performs the specified action for each element in an array.
```javascript
const numbers = [28, 77, 45, 99, 27];

numbers.forEach((value, index, array) => {
  console.log(value);
});
```
# Array.filter()
---
A function that accepts up to three arguments. The filter method calls the predicate function one time for each element in the array.

Returns the elements of an array that meet the condition specified in a callback function.
```javascript
const randomNumbers = [4, 11, 42, 14, 39];
const filteredArray = randomNumbers.filter((value, index, array) => {
  return value > 5;
});
//11,42,14,39
```

# Array.sort()
---
Function used to determine the order of the elements. It is expected to return a negative value if the first argument is less than the second argument, zero if they're equal, and a positive value otherwise. If omitted, the elements are sorted in ascending, UTF-16 code unit order.
`[11,2,22,1].sort((a, b) => a - b)`

```javascript
const myArray = [4, 11, 42, 14, 39];
myArray.sort()
//defaultSortedArray:,11,14,39,4,42
myArray.sort((a, b) => Math.random() - 0.5);
//shuffledArray:,14,42,39,11,4
```
