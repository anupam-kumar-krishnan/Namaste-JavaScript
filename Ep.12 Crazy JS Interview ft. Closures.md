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
- If we change var to let, so the variable will be block scoped here and we cannot access this let a outside
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
- Let's assume that this `outer()` function takes a parameter `b`. In this case, what will happen? How will the _**Closures**_ be?
- So, suppose if I access my `b` in the inner function console.log, it works the same way. Even if it is called outside(return inner), it will work the same way and it will print the `a` and `b` value. <br>
This happens because inner function forms a Closure with it's outer environment and `b` is also a part of an outer environment of inner function. `b` is also treated the same way, and forms a closure with `b` also. 

<b>

```js
function outer(b){
   function inner(){
     console.log(a, b);
   }
  let a = 10;
  return inner;
}

var close = outer("helloworld");
close(); //10 "helloworld"
```
</b>

## _Relation of Scope Chain and Closures_
**_Q. What if your outer function is nested inside a function. What will happen then? So will inner has access to environment of that function also. Is it the case?_** <br>
Ans: This outer function is like nested inside one more function, so it will again forms a Closure with the environment of that function also


<b>

```js
function outest(){
 var c = 20;
 function outer(b){
   function inner(){
      console.log(a, b, c);
    }
    let a = 10;
    return inner;
  }
  return outer;
}
var close = outest()("helloworld");
close(); // 10 "helloworld" 20
```
</b>


- We can access `c` here. Even if it goes outside, it still will remember `c`


- _**Q. What does the below line do in the above example?**_

<b>

```js
var close = outest()("helloworld");
```
</b>

- Ans.: When this outest is called, it returns the outer function and this outer function which is returned, outer function called with a parameter `b`, it returns the inner function and that inner function goes to variable `close` and  we can call close(); 
























