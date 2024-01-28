## _'let & const'_
- _**let**_ & _**const**_ declarations are _**Hoisted**_

## _Comparision of let and var in case of hoisting_
<b>

```js
console.log(b);

let a = 10;
var b = 100;

//undefined (because of hoisting) 
```
</b>

- here, in the above code, we don't get any error. We get `undefined` as a placeholder for `b`
- The memory is allocated to these variables & functions even before a single line of code is executed
- And that is why, even before setting a value of `100` into `b` or declaring a variable `b`,
we can access `b` like the this(above code). 
- Also, we don't get any error, infact we get a special placeholder `undefined`

## _The Argue_
- If a and b both are hoisted, then we should also be able to accesss a like b above
- But this gives an error, `ReferenceError: Cannot access a before initialization`
- That means, I can only access `a` after I assign or initilize some value to `a`

## _Then how to know this variable was hoisted or not_
- Even before a single line of code is executed, we see JavaScript has allocated memory to `a` i.e. undefined
- We have `a` with us in scope and we also have `b` with us in scope and the value for these are `undefined`
- In case of var, it is in the Global Space, but in case of `a` we see some script
![script a](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/e25efe13-bc3b-4bd8-b4a2-f941597f24f0)


- Memory was assigned to `b` to the var declaration and this variable `b` was attached to the global object
- _**Important:**_ But in case of `let` & `const`, they are allocated memeory but they are stored in a different memeory space than global(not on the Global Object now)and you can't access this declaration before you have put in some value in them and that is what is called _**Hoisting**_


<b>

```js
console.log(a);

let a = 10;
var b = 20;

//Cannot access `a` before initialization
```
</b>

## _Temporal Dead Zone🔥_
- The time since when this `let` variable was **_hoisted_** and till it is **_initialized some value_**
- That time between that is known as _**Temporal Dead Zone**_
<b>

```js
1 console.log(a);
2 let a = 10;
3 var b = 100;
```
</b>

- The time between line number 1 and 3, that phase is known as the _**Temporal Dead Zone🔥**_
- Whenever you try to **_access_** a variable in _**Temporal Dead Zone**_, it results in `ReferenceError` and looks like **_`ReferenceError: Cannot access 'a' before initialization`_**
- These variables can only be _**accessed**_ once some **_value is initialized_** in them
- Anything before line number 2(in above code), is _**Temporal Dead Zone**_ for `a`


## _Reference Error_

<b>

```js
console.log(x);
let a = 10;
var b = 100;

//Output
//ReferenceError: x is not defined
```
</b>

- It means, when JavaScript Engine tries to find out this value of `x` in the current scope, it was not able to find it. `x` was not there. There was no reference and hence error says: `ReferenceError: x is not defined`

<b>

```js
console.log(b);
let a = 10;
var b = 100;

//Output
//undefined
```
</b>

- If I try to access `b` here, it gives us `undefined` because memory was allocated to `b` but it was not yet initialized

<b>

```js
console.log(b);
let a = 10;
var b = 100;

//Output
//ReferenceError: Cannot access 'a' before initialization
```
</b>

- But in case of `let`, it throws a `ReferenceError` again, but this time it is a diferent message `ReferenceError: Cannot access 'a' before iniliaization`
- The above `RefernceError: Cannot access 'a' before initialization`(message) states that **_you cannot access `a` before initialization and `a` is in a `Temporal Dead Zone`_**
- And you can access it anywhere after initialization

## _Relation of Global Object & Variables var, let & const_

![this or window accessable let, const   var](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/8b835ac6-c230-43b6-ad44-f77b0a6f06b4)

- If I try to access `b`, I can access it as it gets attached to the **_Window Object_**
- But in case of `a`, it's not attached to _**Window Object**_ as they are maintained in a `Separate Storage(Reserved space for let & const, which is not in Global Space) `

<b>

```js
console.log(b);
let a = 10;
var b = 100;
```
</b>

## _Duplication of Redeclaration of let and const variables_
- This throws an Error and this time it's a Syntax Error
- Error: `SyntaxError: Identifier 'a' has already been declared`
- It won't even execute a single line of code

<b>

```js
let a = 10;

let a = 100;
```
</b>

### _**You cannot use the same name in the same scope again**_

<b>

```js
let a = 10;

let a = 100;
//SyntaxError: Identifier 'a' has already been declared
```
</b>

### _Same case with **_var_**_

<b>

```js
let a = 10;

var a = 100;
//SyntaxError: Identifier 'a' has already been declared
```
</b>


### _But possible in var(only var), `No Error`_

<b>

```js
var b = 10;

var b = 100;
```
</b>

### _**let & const**_
- In case of _**let**_, you just declare and you can initialize later anywhere in the program
- But we can't do this in case of const, const is very strict in this case

<b>

```js
let a;

a=10;
console.log(a);

//10
```
- I _**cannot initilize the value later like let in const**_, if you do, you get SyntaxError:`Missing initializer in const declartion`

```js
let a;
const b;
b=1000;

a=10;

//SyntaxError: Missing initializer in const declartion
```
</b>

### _TypeError in const_
- You are trying to assign any other value to a constant variable
- Why a TypeError? Because this variable b is of type const, it should be initialized & declared together and you cannot assign any value later on


<b>

```js
let a = 1900;

const b = 1000;

b = 10000;

a=10;
console.log(a);


// Uncaught TypeError: Assignment to constant variable
```
</b>

### _Missing initializer in const declartion_

- Missing systax, the syntax expects that if there is const keyword, it expects there would be  equal to some value there

<b>

```js
let a = 1900;
const b;

a=10;
console.log(a);

//SyntaxError: Missing initializer in const declaration
```
</b>

## _Now we have let, var & const. What should we use now?_

### _const_
- Always use **_const_** in the first place, whenever it is needed( value which is not gonna be changed later anytime). When you don't have to assign anything to the same variable use: _**const**_

### _let_
- If not _const_, try to use _**let**_ whenever possible because let has a temporal dead zone, and you will not run into unexpected errors of undefined and all those things.

### _var_
- Keep var aside
- Don't use it now
- Use it Very consciously

## _How to avoid Temporal Dead Zone_
- Always put your declarations & initializations on the top of the scope
- So that as soon as the code starts running. it hits the initialization part at the first and then you do anything with these variables
- Here by putting declarations & initializations on top, we are shrinking the Temporal Dead Zone window to `zero`






















