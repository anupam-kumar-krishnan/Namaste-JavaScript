# _Closures_
- A _**function**_ bundled together with it's _**lexical environment**_ is known as _**Closure**_
- _**A/C to MDN Docs:**_ 
  - A <b><i>Closure</i></b> is the combination of a _**function**_ bundled together(enclosed) with referneces to its _**surrounding state (the lexical environment)**_. 
  - In Other words, a closure gives you access to an _**outer function's scope**_ from an _**inner function.**_
  - JavaScript, a closure is the combination of a function and its lexical environment (the scope in which it was declared). This means that a function, when defined, "remembers" the variables and parameters from its outer (enclosing) function's scope, even after that outer function has finished executing.
    
<b>

```js
function x(){
  var a=7;
  function y(){
     console.log(a);
  }
  y();
}
x();

// Output
// 7
```
</b>

- Here, Inside function y(), it forms a closure which were part of x Lexical Scope 
- The function y() was bind to variable of x(), so that means it forms a CLOSURE and it has access to it's parent lexical scope

![Closures](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/b9e7ea4d-247a-4499-af6b-90923d19f92b)


- _**You can assign function to a variable**_

<b>

```js
function x(){
  var a=function y(){
     console.log(a);
  };
  
  y();
}
x();
```
</b>


- _**You can also pass function in a function**_

<b>

```js
function x(){
  var a=7;
  
  y();
}
x(function y(){
     console.log(a);
  });
```
</b>

- _**You can return these function out of function also**_

<b>

```js
function x(){
  var a=7;
  function y(){
     console.log(a);
  }
  return y;
}
x();
```
</b>

- **_What does this function return?_**

<b>

```js
function x(){
  var a=7;
  function y(){
     console.log(a);
  }
  return y;
}
var z = x();
console.log(z);

// Output
// f y() { 
//   console.log(a);
// }
```
</b>

<b>

```js
function x(){
  var a=7;
  function y(){
     console.log(a);
  }
  return y;
}
var z = x();
console.log(z);
//------
z();

// Output
// f y() { 
//   console.log(a);
// }
// 7
```
</b>

- Here comes _**Closure**_ into picture. 
- Functions are so beautiful that when they are returned from another function, they still maintains their _**Lexical Scope.**_ They remember where they were actually present.
- Though, x no longer exists, but still this y() function remembers  it's lexical scope, where it came from. It remembers that there is something a and it has the binding strong their.
- In Simple words, when you return this y, then not just that function code was returned but a **_Closure_** was returned. Closure with **_function_** along with _**it's lexical scope**_ that was **_returned._**

## _Corner Cases in Closures_


<b>

```js
function x(){
  var a=7;
  function y(){
     console.log(a);
  }
  a=100;
  return y;
}
var z = x();
console.log(z);
//------
z();

// Output
// f y(){
//   console.log(a);
// }
// 100
```
</b>

- The function along with the _**reference to those variables**_ (not the value)
- Here, in the code the reference points to 100, that means that 100 is still in the memory preserved because of **_Closure_** and when x was gone, it was not garbage collected, it will be used later. So that way that **_Closure_** is like giving us **_100._** 

<b>

```js
function z() {
  var b = 900;
  function x() {
   var a=7;
     function y(){
       console.log(a,b);
     }
    y();
   }
   x();
 }
z();
```
</b>


![2 closure ](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/a8d6aeb3-3816-4116-8d90-a9572759447d)

- Here, it forms a Closure along with it's variable b which was it's parent's parent and along with a which is it's parent.

## _Uses of Closures:_
- Module Design Pattern
- Currying
- Functions like once(once which kind of gives you a function which only run once)
- Memoize
- Maintaining state in **_async_** world
- setTimeouts
- Iterators
- and many more...



























