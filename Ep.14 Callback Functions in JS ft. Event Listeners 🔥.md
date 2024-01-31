## _What is Callback function in JavaScript_
- To understand **`Event Loop`** properly, you should know what a _**`Callback Function`**_ is and what are it's uses.
- From previous lectures, we know that functions are `First Class Citizens` in JavaScript. _**First Class Functions**_ means you can take a function and pass it into another function
- And when you take a function and pass it into another funtion is known as _**Callback Function**_

## _Advantages of Callback_
- These _**callback**_ functions are very powerful in JavaScript, it gives _**access**_ to the whole **_Asynchronous World in a Synchronous Single Threaded Language_** <br>
In short, due to _callbacks we can do async things also_

<b>

```js
function x(){

}
x(function y(){

})
```
</b>


- You called this function sometime else in your code, it's not called over here
- You give the responsibility to function y to function x
- Here, you pass this y() inside x(), now it's upto x when it wants to call y()


<b>

```js
setTimeout(function(){
    console.log("timer")
), 5000);

function x(y){
    console.log("x");
    y();
}

x(function y(){
    console.log("y");
})
```
</b>

### _Explanation of Above Code_
- As we know, JavaScript is a Synchronous _**Single Threaded Language**_ i.e. it will execute one line at a time and in order
- First thing, registering a setTimeout. setTimeout will take this function and store it in a separate space and it will attach a timer to it of 5000ms and it will store it
- And as we already know that JavaScript will not wait for setTimeout to finish over here. That's why we say, callback gives us the power of Asynchronicity
- And whatever needs to be done after 5000ms, we are passing that feature or those piece of code as a callback function to the setTimeout. It will be later executed.
- Remember we said `Time, Tide and JavaScript` waits for none. Now the code will move on.
- Till thsi point of time, this 5000ms won't have expired
- Now, it will x(), y() and goes on... and after sometime this 5000ms expire, once this callback function is expired, the callback function is then executed
- _**Output will be:**_

``` 
x
y
timer
```

## _Blocking Main Thread in JavaScript_
- Everything executed on the webpage is executed on the _**Call Stack**_ only
- And if any operation blocks the call stack, that is known as _**Blocking the Main Thread**_
- We should always use **_Async Operations_** for things which take time

## _Creating an Event Listners in JavaScript_

![event listner](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/ba6b591e-01f0-4e91-8988-553f74281277)

- Whenever we click the button, this callback function pushed into the call stack and execute it

## _Closure along with Event Listners in JavaScript_

_**Let's print the number of times button is Clicked**_

```js
let count = 0;
document.getElementById("clickMe").addEventListener("click", function xyz() {
  console.log("Button CLicked", ++count);
});
```

- How can we make sure that count is only used for counting the times btn is clicked
- We use _**Closure**_ for _**Data Hiding**_
- Let's create a _**Closure**_

<b>

```js
function attachEventListeners() {
  let count = 0;
  document.getElementById("clickMe")
   .addEventListener("click", function xyz() {
    console.log("Button CLicked", ++count);
  });
}

attachEventListeners();
```
</b>

- Now this callback funtion over here is forming a Closure with it's **_Outer Scope_**


## _Garbage Collection & remove Event Listeners_

- **_Why do we need to removed EventListeners?_**
   - EventListeners are heavy, that means it takes memory
   - Whenever you attach an EventListener, it kind of attach a Closure 



























