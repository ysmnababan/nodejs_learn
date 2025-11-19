## JavaScript Basics Cheat Sheet

### Comments  
```js
// This is a single-line comment  
/* This is a 
   multi-line comment */  
````

---

### Variables & Data Types

```js
let name = "Alice";      // block-scoped, re-assignable  
const PI = 3.14;         // block-scoped, constant  
var oldVar = true;       // function-scoped (avoid if possible)  

// Data types  
let str = "hello";  
let num = 42;  
let decimal = 3.14;  
let bool = false;  
let nothing = null;  
let notDefined;          // undefined  
let sym = Symbol("id");  
let big = 123456789n;    // BigInt  

let obj = { key: "value", age: 30 };  
let arr = [1, 2, 3];  
```

---

### Operators

```js
// Arithmetic  
let sum = 5 + 3;  
let diff = 10 - 2;  
let prod = 4 * 7;  
let div = 20 / 5;  
let mod = 10 % 3;  
let pow = 2 ** 3;  

// Assignment  
x += y;  
x -= y;  
x *= y;  
x /= y;  
x **= y;  

// Comparison  
a == b;   // equals (type coercion)  
a === b;  // strict equals  
a != b;  
a !== b;  
a > b;  
a < b;  
a >= b;  
a <= b;  

// Logical  
a && b;  
a || b;  
!a;  

// Nullish coalescing  
a ?? b;  

// Ternary  
condition ? expr1 : expr2;
```

---

### Control Flow

```js
// If-else  
if (condition) {  
  // code  
} else if (otherCondition) {  
  // code  
} else {  
  // code  
}  

// Switch  
switch (value) {  
  case 1:  
    // code  
    break;  
  case 2:  
    // code  
    break;  
  default:  
    // code  
}  
```

---

### Loops

```js
// For  
for (let i = 0; i < 5; i++) {  
  // code  
}  

// While  
while (condition) {  
  // code  
}  

// Do...while  
do {  
  // code  
} while (condition);  

// For...of (iterables)  
for (const item of arr) {  
  console.log(item);  
}  

// For...in (object keys)  
for (const key in obj) {  
  console.log(key, obj[key]);  
}
```

---

### Functions

```js
// Function declaration  
function add(a, b) {  
  return a + b;  
}  

// Function expression  
const multiply = function(a, b) {  
  return a * b;  
};  

// Arrow function  
const divide = (a, b) => a / b;  

// Default parameters  
function greet(name = "Guest") {  
  return `Hello, ${name}!`;  
}  

// Rest parameters  
function sumAll(...nums) {  
  return nums.reduce((total, n) => total + n, 0);  
}  

// Immediately Invoked Function Expression (IIFE)  
(function() {  
  console.log("I run right away!");  
})();
```

---

### Objects

```js
const person = {  
  name: "Budi",  
  age: 25,  
  greet() {  
    return `Hi, I'm ${this.name}`;  
  }  
};  

// Access  
person.name;  
person["age"];  

// Destructuring  
const { name, age } = person;  

// Spread operator  
const clone = { ...person };  

// Object utilities  
Object.keys(person);      // [ "name", "age", "greet" ]  
Object.values(person);    // [ "Budi", 25, ƒ ]  
Object.entries(person);   // [ [ "name", "Budi" ], [ "age", 25 ], … ]  
```

---

### Arrays

```js
const fruits = ["apple", "banana", "cherry"];  

// Access  
fruits[0];  

// Modify  
fruits.push("grape");  
fruits.pop();  
fruits.unshift("lemon");  
fruits.shift();  
fruits.splice(1, 1);  // remove 1 element at index 1  
const part = fruits.slice(1, 3);  

// Iterate  
fruits.forEach(item => console.log(item));  

// Higher-order methods  
const upper = fruits.map(f => f.toUpperCase());  
const longNames = fruits.filter(f => f.length > 5);  
const totalLength = fruits.reduce((sum, f) => sum + f.length, 0);  

// Destructuring + rest  
const [first, second, ...rest] = fruits;  
const moreFruits = [...fruits, "kiwi"];
```

---

### ES6+ Features

```js
// Template literals  
const who = "Charlie";  
const message = `Hello, ${who}!`;  

// Destructuring in function parameters  
function print({ name, age }) {  
  console.log(name, age);  
}  

// Classes  
class Animal {  
  constructor(name) {  
    this.name = name;  
  }  
  speak() {  
    console.log(`${this.name} makes a sound.`);  
  }  
}  

class Dog extends Animal {  
  speak() {  
    console.log(`${this.name} barks.`);  
  }  
}  

// Modules (ES6)  
// Export  
export function hello() { console.log("Hello"); }  
export const pi = 3.14;  

// Import  
import { hello, pi } from "./module.js";  
```

---

### Error Handling

```js
try {  
  // code that may throw  
} catch (err) {  
  console.error("Error:", err);  
} finally {  
  // always runs  
}
```

---

### Asynchronous (Basic)

```js
// Promise  
const p = new Promise((resolve, reject) => {  
  setTimeout(() => resolve("done"), 1000);  
});  

p.then(result => console.log(result))  
 .catch(error => console.error(error));  

// Async/Await  
async function run() {  
  try {  
    const result = await p;  
    console.log(result);  
  } catch (err) {  
    console.error(err);  
  }  
}  
run();
```

---

### Debugging

```js
console.log("value:", someVar);  
console.error("This is an error");  

// Use browser dev tools: inspect, set breakpoints, step through code  
```