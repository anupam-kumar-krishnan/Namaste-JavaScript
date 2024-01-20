# _Closures_
- A _**function**_ bundled together with it's _**lexical environment**_ is known as _**Closure**_
- _**A/c to MDN:**_ 
  - A <b><i>Closure</i></b> is the combination of a _**function**_ bundled together(enclosed) with referneces to its _**surrounding state (the lexical environment)**_. 
  - In Other words, a closure gives you access to an _**outer function's scope**_ from an _**inner function.**_
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

