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


- It is a SytaxError because this if expects a statement here(one statement)

<b>

```js
if(true) true;
```
</b>

- This is Valid Now. 

- **_But what if you want to write multiple statements?_**
   - Here, you can use this **_Block_** and write multiple statements
   - So, these Group of multiple stetements can be used in a place where JavaScript expects a Single Statement
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
- If we have same named variable outside & inside the block, then the variable inside the block shadows the variable outside the block
- Also, the value of variable inside the block replaces the value of outer variable because they both are pointing tothe same memory location
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










