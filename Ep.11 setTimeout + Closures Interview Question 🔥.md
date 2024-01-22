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
- _**JavaScript doesn't wait for anyone!!**_ ‼️

## _Print 1, 2, 3, 4, 5 after each & evry second_
- 1 after 1 second
- 2 after 2 second and so on...

<b>

```js
function x(){
 for(var i = 1; i <= 5; i++) {
   setTimeout(function () {
      console.log(i);
   }, i*1000);
}
console.log("Namaste JavaScript");
}
x();

// Namaste JavaScript
// 6
// 6
// 6
// 6
// 6
```
</b>

- When the loop runs the first time, it makes a copy of this funtion, attaches a timer and also remembers the refernce of `i`
- Similarly, these 5 copy of the functions are pointing to same refernce of `i`
-  They are pointing to same reference of `i`, because the environment for all of these functions are same
- All the copies of `setTimeout` callback functions are pointing to same reference of `i`
- JavaScript doesn't wait for anything, it wil run the loop again and again and setTimeout will store that function and JavaScript will move on(It doen't wait for that timer to expire)
- And when the timer expires, it is too late and the value of `i` because the loop was constantly running, so the `i` value became `6`
- And when this callback function runs by that time the value of `i`  is `6` in the `memory location.`

## _How to overcome the problem of printing the same number 6_
- To overcome this problem(`var`), just replace var with `let`
- `let` has a `block scope`, that means for each & every loop iteration, whenever everytime loop runs this `i` is a new variable altogether
- And each time setTimeout is run, this callback function has a new copy of `i` with it
- In Simple terms, ech ad everytime this function is called it is refering to different memory location which is their individual `i`, **_separate copy_** of `i` which were in the scope.

<b>

```js
function x(){
 for(let i = 1; i <= 5; i++) {
   setTimeout(function () {
      console.log(i);
   }, i*1000);
}
console.log("Namaste JavaScript");
}
x();

// Output
// Namaste JavaScript
// 1
// 2
// 3
// 4
// 5
```
</b>

## _using `var`_

<b>

```js
function x(){
 for(var i = 1; i <= 5; i++) {
   function close(x) {  
   setTimeout(function () {
      console.log(x);
   }, i*1000);
  }
  close(i);
}
  console.log("Namaste JavaScript");
}

x();
```
</b>

- Here we created a _**new copy**_ of `i`, everytime _**setTimeout**_ was called
- Everytime this close function is called, has a new copy of `i` in it






















