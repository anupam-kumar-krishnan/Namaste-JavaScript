## _Shortest JavaScript Program_

- Shortest JavaScript Program is an empty JS file
- Even if we haven't written anything, a Global Execution Context is created and sets up the memory space (though there is nothing setup memory, but still it does it's job)
- JavaScript Engine also creates something known as `Window`
- `Window` is a Global Object which is created along with `Global Execution Context`
- Whenever a JavaScript code is run, it creates a `Global Execution Context`, along with `window` and `this` variable is created
- Everywhere JS is running, there must be a `JavaScript Engine` there. For Chrome: v8
- All these JS Engines has responsibility to create this `Global Object`
- In case of browsers, it is known as `window`
- At the global level, `this` is equal to `window`

<b>

```js
this === window 

// true [at global level]
```
</b>

## _Global Space_
- Global Space is nothing but any code in javascript which is not inside a `function`
- Whenever you create any variables or functions in Global Space, these variables & functions get attached to the Global Object i.e. `Window`

<b>

```js
var a = 10;       // not inside any function. So global object

function b() {    // this function not inside any function. So global.
  var x = 5;      // not global as this variable is inside a function
 }

console.log(window.a);  // 10 | gives us "a" value
console.log(this.a);    // 10 | this points to window so it returns "a" value
console.log(a);         // 10 | also gives same "a" value. (if we dont put any . in front of variable, it **assumes variable is in global space**
console.log(x);         // ReferenceError: x is not defined. (tries to find x inside global space, but it isn't there) 
```
</b>











