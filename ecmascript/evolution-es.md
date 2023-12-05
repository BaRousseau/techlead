# Evolution ES

## ES1-2

Pas testable.

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

### "use strict"

Déclarer une variable sans `var` devant, sans puis avec `"use strict"`.

### String[number] access

Multiline strings
String.trim()
Array.isArray()
Array forEach()
Array map()
Array filter()
Array reduce()
Array reduceRight()
Array every()
Array some()
Array indexOf()
Array lastIndexOf()
JSON.parse()
JSON.stringify()
Date.now()
Date toISOString()
Date toJSON()
Property getters and setters
Reserved words as property names
Object methods
Object defineProperty()
Function bind()
Trailing commas

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

Added let and const
Added default parameter values
Added Array.find()
Added Array.findIndex()

## ES2016

Added exponential operator (\*\*)
Added Array.includes()

## ES2017

Added string padding
Added Object.entries()
Added Object.values()
Added async functions
Added shared memory
Allows trailing commas for function parameters

## ES2018

Added rest / spread properties
Added asynchronous iteration
Added Promise.finally()
Additions to RegExp

## ES2019

String.trimStart()
String.trimEnd()
Array.flat()
Object.fromEntries
Optional catch binding

## ES2020

The Nullish Coalescing Operator (??)

## Sources

<https://www.w3schools.com/Js/js_versions.asp>
