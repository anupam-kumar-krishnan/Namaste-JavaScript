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
getName();       //  // in most languages, both lines which are above their declaration will give error. Not in JS though.
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

<b>

```js
getName();
console.log(x);
//var x = 7;

function getName() {
   console.log("Namaste JavaScript");
}
```
</b>

- If we remove `var x = 7;`, as soon as the code runs the first line, JavaScript has not reserved memory for `x` but only for function getName() 
- And the code tries to access `x` but will not be found as we have removed that. There is no value for `x`
- This means now JavaScript will throw an error **`RefferenceError: Reference x is not defined`** i.e. x is not present in the memory(x is nowhere initialized in the program, and we are trying to access the value of x)
<br>

- _**Not defined:**_ We have not initialised the value for variable anywhere in the entire code and in memory space.
- _**Undefined:**_ It is a placeholder that is assigned to a variable by the Javascript Engine until the variable is assigned with some other value.


## _Hoisting_
- _Hoisting is a phenomenon in JavaScript by which we can access variables & functions even before we have initialised it_
- _Hoisting is a concept which enables us to extract values of variables and functions even before initialising/assigning value without getting error_
- **_Definition:_** Hoisting is a JavaScript mechanism where variable and function declarations are put into memory during the compile phase. This means that no matter where functions and variables are declared, they are moved to the top of their scope regardless of whether their scope is global or local

## _Note:_
- Even before code starts executing, memory is allocated to all variables & functions

<b>

```js
function getName(){
    console.log("Namaste JavaScript");
}

console.log(getName);

// Output
// f getName(){
//    console.log("Namaste JavaScript");
// }
```
</b>




## _Arrow Function_
- _**Arrow Functions**_ are Treated as _**variables**_ not _functions_ in JS
<b>

```js
console.log(getName);
console.log(getName2);

var x = 7;

// arrow function, considers as variale in JS
var getName = () => {
  console.log("Namaste JavaScript");
}

// another way of writing function where JS considers it as variable
var getName2 = function() {
  console.log("Namaste JavaScript");
}

// valid function declaration
function functionName() {

}

// Output
// undefined    // it is because they behave as variable and not function.
// undefined
```
</b>

### _Reason of this behaviour_
- When _**getName**_ is an _arrow function_, it behaves just like another _**variable**_
- And JavaScript allocates `undefined` to these functions here(above code getName & getName2)
- And since, it's variable not function, In the memory phase, the _**variables**_ will be initialized as _**undefined**_ and _**functions**_ will get the whole **_function code in their memory_**.




















