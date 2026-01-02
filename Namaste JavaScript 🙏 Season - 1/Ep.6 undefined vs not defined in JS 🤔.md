## _undefined_
- **Definition:**
> In JavaScript, `undefined` is a primitive value and a global property that indicates a variable has been `declared but has not been assigned` a value. It acts as a default placeholder automatically assigned by the JavaScript engine in various scenarios. 
- JavaScript tries to allocate memeory to the variables & function even before we run the code

<b>

```js
=> var a = 7;
```
</b>


- In the above code, with debugger at line var a=7;, JavaScript already reserves a memory for `a` 
- That _**reserved memory**_ has been given a placeholder named as **`undefined`** 
- `undefined` is like a _**placeholder**_ which is placed in the memory

<b>

```js
console.log(a); //undefied
var a=7;

console.log(x); //not defined
```

## _Check if a is undefined_

```js
var a;

console.log(a);

if(a===undefined){
   console.log("a is undefined");
}
else {
   console.log("a is not undefined");
}

// Output
// a is undefined
```

</b>

## _JavaScript is a loosely typed language_
- It means that JS doesn't attaches it's variables to any specific datatypes
- loosely typed language doesn't means JavaScript is weak language. 
In fact, JS is more stronger because it is handling alot of stuff behind the scenes

<b>

```js
var a;
console.log(a); // undefined
a=10;
console.log(a); // 10
a="hello world";
console.log(a); // Hello World
```

</b>

### _Mistakes we should not do_

- It not a good practice to put `undefined` to any variable

<b>

```js
var a = undefined;
```
</b>







