# Evolution ES

"Each Web browser and server that supports ECMAScript supplies its own host environment, completing
the ECMAScript execution environment."
ECMA-262 1st Edition June 1997

## ES1-2 (1997)

- Variables
- Functions
- Basic control flow statements

```js
// Variable in ES1
var mathematician = "John Doe";
console.log(mathematician);

// Function in ES1
function divide(dividend, divisor) {
  // Control Flow in ES1
  if (divisor !== 0) {
    return dividend / divisor;
  } else {
    return 0;
  }
}

// For Loop in ES1
for (let index = 0; index < 10; index++) {
  console.log(divide(index * index, index));
}

// console is a global variable added at runtime.
```

## ES3 (1999)

```shell
npm run es3
```

Added regular expressions
Added try/catch
Added switch
Added do-while

Là on peut voir les limites de es-check, il ne vérifie que la syntaxe.
Alors que la méthode filter n'existe pas encore en es3.

Voici un polyfill de filter :

```js
Array.prototype.filter = function (callBack) {
  var newArray = [];
  for (var i = 0; i < this.length; i++) {
    var result = callBack(this[i], i, this);
    if (result) {
      newArray.push(this[i]);
    }
  }
  return newArray;
};
```

## ES4 (1999)

N'existe pas. Voir 3.1.

## ES5 (2009)

- "use strict"
- String[number] access
- Multiline strings
- String.trim()
- Array.isArray()
- Array forEach()
- Array map()
- Array filter()
- Array reduce()
- Array reduceRight()
- Array every()
- Array some()
- Array indexOf()
- Array lastIndexOf()
- JSON.parse()
- JSON.stringify()
- Date.now()
- Date toISOString()
- Date toJSON()
- Property getters and setters
- Reserved words as property names
- Object methods
- Object defineProperty()
- Function bind()
- Trailing commas

```shell
npm run es5
```

## Bonus 2010

window.onload n'est plus forcément utile.

La balise HTML script accepte defer / async en attribut (2010 = Chrome 8)

```html
<script defer src="./index.js"></script>
```

## ES6 ou ES2015

- Added let and const
- Added default parameter values
- Added Array.find()
- Added Array.findIndex()
- Arrow Functions
- Classes
- Default Parameters
- Destructuring
- Let and Const
- Maps
- Sets
- Template Literals

```js
// Example of let and const in ES6
let name = "John Doe";
const age = 30;

// Example of arrow function in ES6
let add = (a, b) => a + b;
console.log(add(1, 2)); // Output: 3

// Example of template literals in ES6
let message = `Hello, ${name}!`;
console.log(message); // Output: "Hello, John Doe!"

// Example of class in ES6
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    greet() {
        return `Hello, ${this.name}!`;
    }
}
let john = new Person("John Doe", 30);
console.log(john.greet()); // Output: "Hello, John Doe!"
```

## ES2016

- Added exponential operator (\*\*)
- Added Array.includes()

```js
// Example of exponentiation operator in ES7
let square = 2**2;
console.log(square); // Output: 4

// Example of Array.prototype.includes in ES7
let numbers = [1, 2, 3, 4, 5];
console.log(numbers.includes(3)); // Output: true
```

## ES2017

- Object.values/Object.entries
- String padding
- Object.getOwnPropertyDescriptors
- Trailing commas in function parameter lists and calls
- Async functions
- Shared memory and atomics

## ES2018

- Lifting template literal restriction.
- s (dotAll) flag for regular expressions.
- Regexp named capture groups.
- Rest/spread properties.
- Regexp lookbehind assertions.
- Regexp Unicode property escapes.
- Promise.prototype.finally.
- Asynchronous iteration.

## ES2019

- Array#{flat,flatMap}
- Object.fromEntries
- String#{trimStart,trimEnd}
- Symbol#description
- try { } catch {}// optional binding
- JSON⊂ECMAScript
- well-formed JSON.stringify
- stable Array#sort
- revised Function#toString
- BigInt primitive type (stage 3)
- Dynamic import (stage 3)
- Standardized globalThis object (stage 3)

## ES2020

- String.prototype.matchAll
- import()
- BigInt
- Promise.allSettled
- globalThis
- for-in mechanics
- Optional Chaining
- Nullish coalescing Operator

## Sources

<https://www.w3schools.com/Js/js_versions.asp>
