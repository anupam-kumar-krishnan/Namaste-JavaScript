## _setTimeout_

<b>

```js
function x(){
  var i = 1;
  setTimeout(function(){
   console.log(i);
 }, 1000)
}

x();

// 1 | Prints 1 after 1 second
```
</b>

<b>

```js
function x(){
  var i = 1;
  setTimeout(function(){
   console.log(i);
  }, 3000);
 console.log("Namaste JavaScript");
}

x();

// Namaste JavaScript
// 1 | Prints 1 after 3 second
```
</b>

- Here, in the above code, first `Namaste JavaScript` will be printed and then after 3 second value of `i` will be printed i.e. `1`
- JavaScript doesn't wait for anyone








