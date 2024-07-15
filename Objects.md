#### Objects are a fundamental part of JavaScript and are used to store collections of data and more complex entities. Let's dive into how to create and manipulate objects in JavaScript.

### Creating Objects

#### 1. Object Literals

The most common way to create an object is by using an object literal. This is a comma-separated list of key-value pairs wrapped in curly braces `{}`.

```javascript
const person = {
    name: "Alice",
    age: 30,
    job: "Engineer"
};
```

#### 2. Using the `new Object()` Syntax

You can also create an object using the `new Object()` syntax, although this is less common.

```javascript
const person = new Object();
person.name = "Alice";
person.age = 30;
person.job = "Engineer";
```

### Accessing Object Properties

You can access object properties using either dot notation or bracket notation.

#### Dot Notation

```javascript
console.log(person.name); // Output: Alice
console.log(person.age);  // Output: 30
```

#### Bracket Notation

Bracket notation is useful when the property name is dynamic or not a valid identifier.

```javascript
console.log(person["name"]); // Output: Alice
console.log(person["age"]);  // Output: 30

const property = "job";
console.log(person[property]); // Output: Engineer
```

### Adding and Modifying Properties

You can add new properties or modify existing ones using dot or bracket notation.

```javascript
person.city = "New York"; // Adding a new property
person.age = 31;          // Modifying an existing property

console.log(person.city); // Output: New York
console.log(person.age);  // Output: 31
```

### Deleting Properties

You can delete a property from an object using the `delete` operator.

```javascript
delete person.job;
console.log(person.job); // Output: undefined
```

### Methods in Objects

Objects can also have methods, which are functions stored as object properties.

```javascript
const person = {
    name: "Alice",
    age: 30,
    greet: function() {
        console.log("Hello, my name is " + this.name);
    }
};

person.greet(); // Output: Hello, my name is Alice
```

### Iterating Over Object Properties

You can iterate over an object's properties using a `for...in` loop.

```javascript
for (let key in person) {
    if (person.hasOwnProperty(key)) {
        console.log(key + ": " + person[key]);
    }
}
// Output:
// name: Alice
// age: 30
// greet: function() { ... }
```

### Object Methods

JavaScript provides several built-in methods for working with objects.

#### `Object.keys()`

Returns an array of the object's own property names.

```javascript
const keys = Object.keys(person);
console.log(keys); // Output: ["name", "age", "greet"]
```

#### `Object.values()`

Returns an array of the object's own property values.

```javascript
const values = Object.values(person);
console.log(values); // Output: ["Alice", 30, function() { ... }]
```

#### `Object.entries()`

Returns an array of the object's own key-value pairs.

```javascript
const entries = Object.entries(person);
console.log(entries); // Output: [["name", "Alice"], ["age", 30], ["greet", function() { ... }]]
```

### Nested Objects

Objects can contain other objects, allowing you to create complex data structures.

```javascript
const person = {
    name: "Alice",
    age: 30,
    address: {
        street: "123 Main St",
        city: "New York",
        zip: "10001"
    }
};

console.log(person.address.city); // Output: New York
```

### Summary

- **Creating Objects**: Using object literals or `new Object()`.
- **Accessing Properties**: Using dot notation or bracket notation.
- **Adding/Modifying Properties**: Using dot or bracket notation.
- **Deleting Properties**: Using the `delete` operator.
- **Methods**: Functions stored as object properties.
- **Iterating**: Using `for...in` loop.
- **Object Methods**: `Object.keys()`, `Object.values()`, `Object.entries()`.
- **Nested Objects**: Objects within objects for complex data structures.

Feel free to ask if you
