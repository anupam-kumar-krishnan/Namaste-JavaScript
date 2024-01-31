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












