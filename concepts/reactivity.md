# Reactivity

Reactivity : A **declarative** programming model that updates automatically based on changes to **state**.

State : Values that aren't static. Variables, properties, values inside arrays or collections.

Root state and derived state :

```js
// Values a and b are root state
let a = 1;
let b = 2;

// Value of aPlusB is a derived state of a and b
function aPlusB() {
  return a + b;
}
```

In declarative programming, the programmer describes what they want to happen, without worrying about the details of how it is done.

In imperative programming, the programmer describes the exact steps for how something should be done.

```js
let a = 1;
let b = 2;

let aPlusB = a + b;

// update `a`
a = 4;
aPlusB = a + b;

// update `b`
b = 7;
aPlusB = a + b;
```

<https://www.pzuraq.com/blog/what-is-reactivity>
