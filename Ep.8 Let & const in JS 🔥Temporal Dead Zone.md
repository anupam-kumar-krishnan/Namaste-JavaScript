## _'let & const'_
- _**let**_ & _**const**_ declarations are _**Hoisted**_

## _Comprision of let and var in case of hoisting_
<b>

```js
console.log(b);

let a = 10;
var b = 20;

//undefined (because of hoisting) 
```
</b>

- If a and b both are hoisted, then we should also be able to accesss a like b above
- That means, if I do a console.log after we have initialized or put in some value in a, the we are able to access it

## _Then how to know this variable was hoisted or not_
- Even before a single line of code is executed, we see JavaScript has allocated memory to `a` i.e. undefined
- We have `a` with us in scope and we also have `b` with us in scope and the value for these are `undefined`
- In case of var, it is in the Global Space, but in case of `a` we see some script
- Memory was assgned to `b` to the var declaration and this variable `b` was attached to the global object
- But in case of `let` & `const`, they are allocated memeory but they are stored in a different memeory space than global(not on the Global Object now)and you can't access theis declaration before you have put in some value in them) and that is what is called _**Hoisting**_


<b>

```js
console.log(a);

let a = 10;
var b = 20;

//Cannot access `a` before initialization
```
</b>

## _Temporal Dead Zone🔥_
- The time since when this let variable was hoisted and till it is initialized some value
- That time between that is known as _**Temporal Dead Zone**_

```js
1 console.log(a);
2 let a = 10;
3 var b = 100;
```
- The time between line number 1 and 3, that phase is known as the Temporal Dead Zone
- Whenever you try to access a variable in Temporal Dead Zone, it results in `ReferenceError` and looks like **_`ReferenceError: Cannot access 'a' before initialization`_**
- Thses variables can only be accessed once some value is initialized in them





