## _'let & const'_
- _**let**_ & _**const**_ declarations are _**Hoisted**_

## _Comprision of let and var in case of hoisting_
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




