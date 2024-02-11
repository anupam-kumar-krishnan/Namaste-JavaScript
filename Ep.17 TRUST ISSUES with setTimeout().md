# _TRUST ISSUES 💔 with setTimeout()_

![trust issues - setTimeout -](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/86e5e7a1-7e83-40c8-b727-ce38fb15b56d)

- A **_`setTimeout`_** with a delay of **5000ms** _doesn't always exactly wait_ for **5s**
- There are **_Trust Issues_**
- **_`setTimeout`_** doesn't gurantee that the Callback method will be exactly after 5s. It might take 6s or may be 10s
- This all depends on the _**Call Stack**_ <br><br>
- **_Let's try to Understand with an example:_**
- What happens when you run a JavaScript Code, a **_Global Execution Context_** is created and **pushed** inside the **_Call Stack_**
- Now, the code will run line by line
- The first line, **_`console.log("Start")`_**, this will print **_Start_** in the **conosle** using the **_console of Web API_**
- The the code moves on to the second line
- When we see the **_`setTimeout()`_**, it actually **registers** this **_callback method_** over here into the **_Web APIs environment_** and it also has a **_timer_** of 5000ms started 
- Callback function is in the **_Web APIs environment_** waiting for its turn to be **executed** once the _**Timer**_ expires
- But JavaScript doesn't wait for anything, it just **_registers_** the **_`setTimeout()`_** and moves to the next line
- And now **_`End`_** is printed in the console
<br>

- Suppose, we have 1 million line of code after **_`console.log("End");`_**  which take a lot of time to run. Supose 10 sec to run.
- In that case, the GEC won't go our of _Call Stack_ , it will wait for 10sec but the timer was running for 5 sec has already expired long back
- And the _**Callback function**_ has already been pushed inside the _**callback Queue**_
- Now, **_Event Loop_** is constantly checking whether the _**Call Stack**_ is **_Empty or not_**
- Event loop is checking if GEC is pushed off the Stack then it will push the Callback method
- But GEC will not get popped off from the stack before 10s
- So, now **_Callback method_** is waiting in the **_Callback Queue_** and _**GEC**_ is getting executed till 10s/
- So now **_What will happen? When the Callback function will get a chance to execute_**
  - The answer is after _**10sec**_
  - Though _**`setTimeout()`**_ was for 5000ms, but the _**Callback method**_ in **_Callback Queue_** will wait for the **_Global Execution Context_** to move out from the **_Call Stack_**
- The _**Callback method**_ will wait for the whole program to execute before the  _**Callback method**_ can be pushed inside the **_Call Stack_**
- And this is also known as the **_Concurreny Model in JavaScript_**

- After 10s, the GEC will be popped off and **_Callback method_** will be **pushed** inside the **_Call Stack_**
- And then the function cb() is executed line by line
- It sees the console of `callback` in the cb() function and it prints _**`Callback`**_ in the console after 10s

- But when we wrote the code, we actually expected it to run after 5000ms. That is why we say **_`setTimeout() has TRUST ISSUE`_**

### _Don't block your Main Thread_
- This means we shouldn't block this Call Stack. We shouldn't have anything inside the Call Stack which is blocking the _**Main Thread**_
- Because if this _**Call Stack**_ is _**not empty**_ , it _**cannot procees any other event**_

### _Example_

<b>

```js
console.log("Start");

setTimeout(function cb()) {
    console.log("Callback");
}, 5000);

console.log("End");

// 'Start' will be printed
// callback will be registered
// along with callbacka timer will be stared of 5000ms
// 'End' will be printed
// and after 5000ms 'Callback' will be printed
```

### _Output_

```txt
Start
End
Callback //prints after 5000ms
```

</b>

## _How to Wait for 10s_

<b>

```js
console.log("Start");

setTimeout(function cb()) {
    console.log("Callback");
}, 5000);

console.log("End");

// million
// the below code will block the Main Thread
let startDate = new Date().getTime();
let endDate = startDate;
while(endDate < startDate + 10000) {
   endDate = new Date().getTime();
}

console.log("While Expires");
```

### _Output_

```
Start
End
While Expires
Callback
```

</b>

## _What if the setTimeout is ZERO_
- **_What is the meaning of delaying a function for zero seconds?_**
   - What people think that as the delay is of zero seconds, it doesn't have to ait for even a single second
   - But that is not the case. 
   - Even if the timer over here is 0ms, the function has to go through the _**Queue**_
   - That means, it will register a _**Callback**_ into the Web API environment and JavaScript will not wait for anything and logs **`End`**
  - Though the timer has expired long back, it moves into the **_Callback Queue_** and it will get the chance to execute once the **_Call Stack_** is **Empty**
  - After _**Global Execution Context**_ is **out** of the **_Call Stack_** then only this **_Callback Function_** will get a _chance to be Executed_



<b>

```js
console.log("Start");

setTimeout(function cb()) {
    console.log("Callback");
}, 0);

console.log("End");

// Output
// Start
// End
// Callback
```
</b>

### _Why would someone delay for 0s_
- If you want to **_defer_** some piece of code
- You don't have to execute that piece of code at that point of time

### _Concurrency Model in JavaScript_
- The concurrency model of JavaScript is based on the concept of an “event loop”. This model enables JavaScript to carry out non-blocking I/O operations despite being a single-threaded language. This capability is made possible by offloading certain operations to the system kernel whenever possible.
































































