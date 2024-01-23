## _What is a Closure in JavaScript?_
- A function along with a reference to it's outer environment together forms a Closure
- In Other words, Closure is a combination of function and it's lexical scope bundled together forms a `Closure`
- It's like each & every function in JavaScript has access to it's outer lexical environment(access to the variable & function which are present in the environment of it's parent)
- Even if some function executed in some other scope & not in it's original scope, it still remembers it's outer lexical environment where it was originally present in the code.

<b>

```js
function outer(){
 var a = 10;
   function inner(){
     console.log(a);
   }
  return inner;
}

outer()(); //10
```
</b>

## _Use of double Parenthesis_
- ()() = this means calling the inner function in the above example
- outer() = this returns the inner function
- outer()() = this will call the inner function in the same line itself
- Similary we can write outer()(), like this also:

<b>

```js
function outer(){
 var a = 10;
   function inner(){
     console.log(a);
   }
  return inner;
}

var close = outer();
close(); //10
```
</b>

## _What will happen if we move variable declaration outside inner function_
- Will this still forms a _**Closure?**_ : It will still form a _**Closure,**_ and will work the same way
- This inner function forms a closure with it's outside environment and not in a particular sequence where it is present in the code.

<b>

```js
function outer(){
   function inner(){
     console.log(a);
   }
  var a = 10;
  return inner;
}

var close = outer();
close(); //10
```
</b>

## _What if we change var a to let a_
- Considering that `let` is _**Block Scoped**_
- If we change var to let, so the variable will be bock scoped here and we cannot access this let a outside
- But still, it behaves the same way
- It still forms a closure, even if it is a `let`

<b>

```js
function outer(){
   function inner(){
     console.log(a);
   }
  let a = 10;
  return inner;
}

var close = outer();
close(); //10
```
</b>

## _Are function parameters closed over?_

















