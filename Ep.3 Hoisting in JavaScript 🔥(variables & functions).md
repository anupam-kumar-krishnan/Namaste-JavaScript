## _Hoisting_

<b>

```js
var x = 7;

function getName() {
   console.log("Namaste JavaScript");
}

getName();
console.log(x);

// Output
// Namaste JavaScript
// 7
```
```js
getName();
console.log(x);

var x = 7;

function getName() {
   console.log("Namaste JavaScript");
}

// Output
// Namaste JavaScript
// undefined
```
```js
getName();
console.log(x);

function getName() {
   console.log("Namaste JavaScript");
}

// Output
// Namaste JavaScript
// not defined
```

</b>

## _Isn't `undefined` & `not defined` the same thing? NO_
This all happened due to the phenomenon of hoisting in JavaScript

## _Hoisting_














