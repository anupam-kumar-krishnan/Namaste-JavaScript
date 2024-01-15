## _Shortest JavaScript Program_

- Shortest JavaScript Program is an empty JS file
- Even if we haven't written anything, a Global Execution Context is created and sets up the memory space (though there is nothing setup memory, but still it does it's job)
- JavaScript Engine also creates something known as `Window`
- It creates the `GEC`, the `window` and the `this` variable
- Everywhere JS is running, there must be a `JavaScript Engine` there. For Chrome: v8
- All these JS Engines has responsibility to create this global object
- In case of browsers, it is known as `Window'
- At the global level, `this` is equal to `window`

<b>

```js
this === window -> true (at global level)
```
</b>

## _Global Space_
- Global Space is nothing but any code in javascript which is not inside a `function`
- Whenever you create any variables or functions in Global Space, these varibales & functions get attached to the Global Object i.e. `Window`

<b>

```js
console.log(this.a) 
console.log(window.a)  
console.log(a)
```
</b>











