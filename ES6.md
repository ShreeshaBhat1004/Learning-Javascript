### 1. `let` and `const`

#### `let`
- **Block Scope**: Unlike `var`, which is function-scoped, `let` is block-scoped. This means that a variable declared with `let` is only accessible within the block it was declared in.
- **Reassignment**: Variables declared with `let` can be reassigned.

```javascript
let x = 10;
if (true) {
    let x = 20; // This x is different from the x outside the block
    console.log(x); // 20
}
console.log(x); // 10
```

#### `const`
- **Block Scope**: Similar to `let`, `const` is also block-scoped.
- **Immutability**: Variables declared with `const` cannot be reassigned. However, if the variable is an object or array, the contents can still be modified.

```javascript
const y = 30;
y = 40; // Error: Assignment to constant variable

const obj = { name: 'Alice' };
obj.name = 'Bob'; // This is allowed
console.log(obj.name); // Bob
```

### 2. Template Literals

Template literals provide an easier way to create strings and include expressions within them.

```javascript
const name = 'John';
const age = 25;
const greeting = `Hello, my name is ${name} and I am ${age} years old.`;
console.log(greeting); // Hello, my name is John and I am 25 years old.
```

### 3. Destructuring

Destructuring allows you to unpack values from arrays or properties from objects into distinct variables.

#### Array Destructuring

```javascript
const numbers = [1, 2, 3];
const [a, b, c] = numbers;
console.log(a, b, c); // 1 2 3
```

#### Object Destructuring

```javascript
const person = { name: 'Alice', age: 30 };
const { name, age } = person;
console.log(name, age); // Alice 30
```

### 4. Spread and Rest Operators

#### Spread Operator

The spread operator (`...`) allows you to spread elements of an array or object.

```javascript
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5, 6];
console.log(arr2); // [1, 2, 3, 4, 5, 6]

const obj1 = { a: 1, b: 2 };
const obj2 = { ...obj1, c: 3 };
console.log(obj2); // { a: 1, b: 2, c: 3 }
```

#### Rest Operator

The rest operator (`...`) allows you to collect all remaining elements into an array.

```javascript
function sum(...args) {
    return args.reduce((acc, val) => acc + val, 0);
}
console.log(sum(1, 2, 3, 4)); // 10
```

### 5. Promises and `async/await`

#### Promises

Promises provide a way to handle asynchronous operations. They can be in one of three states: pending, fulfilled, or rejected.

```javascript
const promise = new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve('Success!');
    }, 1000);
});

promise.then((message) => {
    console.log(message); // Success!
}).catch((error) => {
    console.error(error);
});
```

#### `async/await`

`async/await` is syntactic sugar built on top of promises, making asynchronous code look and behave more like synchronous code.

```javascript
async function fetchData() {
    try {
        const response = await fetch('https://api.example.com/data');
        const data = await response.json();
        console.log(data);
    } catch (error) {
        console.error('Error:', error);
    }
}

fetchData();
```

### 6. Modules

ES6 introduced a standardized module system, allowing you to import and export functionalities between different JavaScript files.

#### Exporting

```javascript
// math.js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
```

#### Importing

```javascript
// main.js
import { add, subtract } from './math.js';
console.log(add(2, 3)); // 5
console.log(subtract(5, 2)); // 3
```

### 7. Error Handling

ES6+ provides better ways to handle errors, especially in asynchronous code.

#### Try-Catch

```javascript
try {
    throw new Error('Something went wrong!');
} catch (error) {
    console.error(error.message); // Something went wrong!
}
```

#### Error Handling in `async/await`

```javascript
async function fetchData() {
    try {
        const response = await fetch('https://api.example.com/data');
        if (!response.ok) {
            throw new Error('Network response was not ok');
        }
        const data = await response.json();
        console.log(data);
    } catch (error) {
        console.error('Fetch error:', error);
    }
}

fetchData();
```

### Summary

- **`let` and `const`**: Block-scoped variable declarations.
- **Template Literals**: Easier string creation with embedded expressions.
- **Destructuring**: Unpack values from arrays or objects.
- **Spread and Rest Operators**: Spread elements or collect remaining elements.
- **Promises and `async/await`**: Handle asynchronous operations more effectively.
- **Modules**: Import and export functionalities between files.
- **Error Handling**: Improved ways to handle errors, especially in asynchronous code.

These ES6+ features have made JavaScript more powerful, readable, and easier to work with. If you have any specific questions or need further examples, feel free to ask!
