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

```js
getName();
console.log(x);
//var x = 7;

function getName() {
   console.log("Namaste JavaScript");
}
```

- If we remove `var x = 7;`, as soon as the code runs the first line, JavaScript has not reserved memory for `x` but only for function getName() 
- And the code tries to access `x` but will not be found as we have removed that. There is no value for `x`
- This means now JavaScript will throw an error **`RefferenceError: Reference x is not defined`** i.e. x is not present in the memory(x is nowhere initialized in the program, and we are trying to access the value of x)

## _Hoisting_
- Hoisting is a phenomenon in JavaScript by which we can access variables & functions even before we have initialised it
- **_Definition:_** Hoisting is a JavaScript mechanism where variable and function declarations are put into memory during the compile phase. This means that no matter where functions and variables are declared, they are moved to the top of their scope regardless of whether their scope is global or local

## _Note:_
- Even before code starts executing, memory is allocated to all variables & functions

## _Arrow Function_

<b>

```js
getName();
console.log(x):
console.log(getName);

var x = 7;

var getName = () => {
  console.log("Namaste JavaScript");
}

// another way of writing this where js considers function as variable
// var getName2 = function() {
// }


// Output
// UnCaught TypeError: getName is not a function
```
</b>

- When getName is an arrow function, it behaves just like another variable
- And JavaScript allocates `undefined` to these functions here(above code getName & getName2)



















