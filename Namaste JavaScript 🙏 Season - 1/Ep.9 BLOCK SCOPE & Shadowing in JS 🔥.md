## _What is a Block in JS?_
- A Block is defined by `Curly Braces`
```js
{
}
```
- _**Block**_ is also known as compound statement
- A Block is used to Combine multiple JavaScript Statements into one Group

<b>

```js
{
  //Compound Statement
  var a = 10;
  console.log(a);
}
```
</b>

- **_Why do we need to Group all these statements together?_**
  - We need to use these statements together in a block so that we can use multiple statements in a place where JavaScripts expects only one statement

<b>

```js
if(true)

//Output
//Uncaught SyntaxError: Unexpected end of input
```
</b>


- It is a Syntax Error because this if expects a statement here(one statement)

<b>

```js
if(true) true;
```
</b>

- This is Valid Now. 

- **_But what if you want to write multiple statements?_**
   - Here, you can use this **_Block_** and write multiple statements
   - So, these Group of multiple statements can be used in a place where JavaScript expects a Single Statement
   - And that is the reason why we often use `if` without any `curly braces {}` right. If in itself doesn't have any curly braces in it's syntax.

## _What is a Block Scope?_

<b>

```js
{
  var a = 10;
  let b = 20;
  const c = 30;
}
```
</b>

- As we can see from the image below, let & const are in Block Scope and var a is in Global Scope
- This is why the Satement comes into picture: <b>_"let & const are Block Scoped"_</b>
- This statement means let & const are stored in a sparate memeory space which is reserved for this block
- These variable `let & const` are no longer accessable `outside the scope` whereas you can access this `var` outside also as it is in the `Global Space`

<b>

```js
{
  var a = 10;
  let b = 20;
  const c = 30;
  console.log(a);
  console.log(b);
  console.log(c);
}

console.log(a);
console.log(b);
console.log(c);


//Output
//10
//20
//30
//ReferenceError: b is not defined
```
</b>

- The error comes at b as b was not in the `Global Scope` <br>

![block scope](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/e7836cee-8eda-4126-806c-bb84c67d5838)


## _What is Shadowing in JavaScript?_
- If we have same named variable outside & inside the block, then the variable inside the block __**shadows**_ the variable outside the block
- Also, the value of variable inside the block replaces the value of outer variable because they both are pointing to the same memory location

<b>

```js
var a = 100;

{
  var a = 10;
  let b = 20;
  const c = 30;
  console.log(a);
  console.log(b);
  console.log(c);
}
console.log(a);


// Output
// 10
// 20
// 30
// 10

```
</b>

## _Shadowing in function_

<b>

```js
var c = 100;
function x() {
 var c = 30;
 console.log(window.c);
 window.c = 20;
}
x();
console.log(c);

//Output
//30
//100
```
</b>

## _Illegal Shadowing_
- **_What if you shadow a let variable using a var variable which is inside the block_**
   - If you want to shadow let variable inside the block scope using var, you cannot do that(Illegal Shadowing)
- It is like Illegal Shadowing, you cannot just do the shadowing
- But what if you shadow let variable inside the block scope using let, this is okay

<b>

```js
let a = 20;
{
 var a = 20;
}

//Output
//Uncaught SyntaxError: Identifier 'a' has already been declared
```
</b>


## _Allowed Shadowing:_

<b>

```js
let a = 20;
{
 let a = 40;
}

```
```js
var a = 20;
{
 let a = 20;
}

```
</b>

## _Arrow Function_
- Wether you declare you function with function keyword or an arrow function, we feel that those might have different scope but they are exactly same
- Thus all the rules which work on function, works the same for arraow function too



















