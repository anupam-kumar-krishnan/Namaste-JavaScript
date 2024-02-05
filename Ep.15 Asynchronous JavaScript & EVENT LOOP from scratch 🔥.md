# _Asynchronous JavaScript & EVENT LOOP from scratch 🔥_

## _Topics Covered_
- Event Loop
- Callback Queue
- Microtask Queue
- How everything is working inside the browser
<br><br>

### _Points_
- So JavaScript is a Single Threaded Language. 
- It has one call Stack and it can do only one task at a time.
- This call stack is present inside the JavaScript Engine
- And all the code of JavaScript is executed inside the **_Call Stack_**
<br><br>
- _**Let's see with an Example Now:**_

![call stack example in event loop](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/a54300dd-b42c-4b41-8dd9-afab642735fd)


- Remember, _**Time, Tide and JavaScript waits for none**_ 
- As all JavaScript code is executed over here(in the above example Image)
- And this Call Stack won't wait for anything, if anything comes inside this call stack, it quickly executes<br><br>
- But hold on, what if we need to wait for something.
- Suppose, we have a program or a script which needs to be run after 5seconds.
   - Can we do that? No, we can't do that because whatever comes inside this call Stack gets quickly executed
   - If you give a script and say that execute it 5seconds later then it cannot do that because it(call stack) doesn't have a timer.
<br><br>
- Suppose we have to keep the track of time and we have to execute some piece of code after certain delay. We will need some extra **_Super Powers._** That Super Powers of **_Timers_** 

## _Super Powers of Browsers_
- Timer
- Local Storage
- Bluetooth
- Location
- Search
- Page being rendered
- URL and many more...

![Super Power of Browsers](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/2efdcfd2-1b91-4794-99de-7cdd6b86da40)


- Suppose in JavaScript Code which is running in Global Execution Context(which is inside Call Stack) need access to these Super Power of Browsers. Wee need to have that kind of connection.

- This JS Engine needs some way to access those Super Powers of Browsers.

## _These are not a part of JavaScript_
- setTimeout()
- Document(DOM)
- fetch
- console
- These are part of _**Browsers**_


## _Let's see how we can access Super Powers of Browsers_
# _Web APIs_
- setTimeout()
- DOM APIs
- fetch()
- Local Storage
- Console
- Location


![Web APIs](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/2e4816f6-6670-47ed-b3af-959592196114)



- **_Browser's_** gave us **_access_** to these Super Powers inside this JS or Call Stack or JavaScript Engine to use these **_Super Powers_**

- Suppose you have to use the Timer Super Power inside the browser. So it gives us access to `setTimeout()`
- Suppose if we have to access the DOM tree(HTML5), this browsers gives  us access to DOM tree by DOM APIs
- Similarly, fetch gives us the access to make connections to the other servers(like the external servers)
- And we get it inside the _**Call Stack**_ because of the _**Global Object i.e.(window)**_
- In case of browsers, browsers gives _**JavaScript Engine**_ the facility to use all these Super Power through a **keyword** known as _**window**_

## _How setTimeout Works behind the scenes in Browsers_
### _Example 1_
![setTimeout](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/28f9f206-8b7b-4c84-b3f0-07ff4fee2efd)

### _**Let's run the code line by line**_

![Code before execution](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/09b92c04-4b17-4939-9b09-76ed5f364a01)

- **`console.log`** => this basically calls the _**Web APIs**_ and it internally makes a call to actually modify or log something inside the _**`console`**_
- You can access this **_console_** or do a **_console.log_** just because you have this **_console API_** and this API is plugged through **_`window`_** to your **_JavaScript Code_**
- Now, we move to the next line, **`setTimeout`** => this `setTimeout` will basically go and _**call**_ this _**Web API**_ and this gives us **_access_** to this **_Timer feature of this browser._**
- And this setTimeout, take a callback function and some delay.
- When you pass this function to setTimeout, this basically registers a callback
- And bacause we pass this _**delay**_, it also starts a timer of _**5000ms**_
- And JavaScript code moves to the next line, it doesn't wait for anyone
- Moving to the next line, it sees _**`console.log("End");`**_ , and again it calls the console from the Web APIs through `window` and logs this **_`End`_** in the console.
- Now this `Timer` is still running, it is just count 5000ms and we are done with executing all our code
- And once all our code is done executing, the _**Global Execution Context**_ just pops of the stack 
- And meanwhile all this is happening, this timer is still running, doing a countdown og 5, 4, 3, .... and as soon as this timer expires, this **_callback funtion(cb)_** needs to be executed 
- And because we know, all our code in JavaScript is Executed inside this _**Call Stack**_ , we somehow need this callback function(cb) inside this **_Call Stack_**
- This _Call Stack_ job is to quickly execute whatever comes inside it(as it is empty currently)

![Code after execution](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/73b51dc8-bbbb-45b9-b6be-29cf3c320581)


## _Event Loop & Callback Queue_

![event loop   callback before](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/e9c853e1-0591-419a-a91f-d699397eb739)


- Now comes into the picture the _**Event Loop**_ and _**Callback Queue**_
- As we know, we somehow needs this _Callback(cb)_ in the _**Call Stack.**_ But it **_can't go directly._**
- How does this Callback function (cb) go to the _**Call Stack**_
  - It wil go to the _Call Stack_ through this **_Callback Queue_**
  - So when the **timer expires**, this **callback** function is put inside the **_Callback Queue_**
  - So as soon as the **5000ms** timer expires, the _**callback function**_ over here is pushed inside the **_Callback Queue_**

- The job of the **_Event Loop_** is to _check the Callback Queue_ and put the **_functions_** of the Callback Queue into the **_Call Stack_**
- So Event Loop over here acts like a Gate Keeper and it checks whether we have something in the Callback Queue and if we have something, it finds the **_callback_** method in **_Callback Queue_**, it just pushes inside the **_Call Stack_** and Call Stack quickly executes the _**Callback function**_
- Callback function executes the same way as JavaScript usually executes. It creates an Execution Context, pushes that Callback inside it and it runs this callback function line by line over here, it sees the **_`console.log("Callback");`_** and when it sees the console it goes to the console(in the Web API) and actually logs it into the console.

![event loop   callback after execution](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/70d56acc-49a3-4ce8-9a72-6570d4ea0176)



## _How Event Listeners Work_
### _Example 2_
![Event Listener before Execution](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/b4ab4ef0-b88b-4fa8-9713-f0f0ef5f9192)

![2nd step - final](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/db12d1a7-1b21-453e-8841-030270c62b31)

![3](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/38c49573-5a1f-4108-8908-49451da6387f)

![4](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/59ce718b-57a1-4e76-ade3-7fecca37c1a6)




- Whenever you run a JavaScript code, a Global Execution Context(GEC) is created and pushed inside the **_Call Stack_**
- Code is executed line by line
- It moves to the first line and sees the `console.log("Start");` and it goes to the console(which is inside Web API, calls this method - Web API method) and logs in the console over here
- Now code moves to the next line, **_`document.getElementById("btn").addEventListener("click" function cb()`_** ,  this addEventListener is another Super Power which is given by the _Browser_ to the **_JavaScript Engine_**  through the `window` object in form of a Web API which is the **_`DOM API`_**
- So whenever you do something like **_`document.`_** it basically calling the _**DOM APIs**_
which basically in turn _**fetches**_ something from the **_Document Object Model[DOM](it is like the HTML source code_**
- This _**DOM API**_ basically **access** the **_HTML code_** and tries to find out a _**button**_ with some `id` and **return** it
- And if you are putting this **`.addEventListener`**, this also registers a `Callback` on an Event and that Event is _**`Click`**_
- _**How **`.addEventListener`** registers a `Callback` on an Event?**_
    - Over here inside the Web APIs environment, a **`Callback`** will be registered and an **Event** will be attached to it.
    - So this is known as **`Registering a Callback`** 
- Now, JavaScript will move on and execute the **`console.log("End");`**
- Thereaftre, there is nothing to execute over here, so the **_Global Execution Context_** also **_pops off_** from the _Call Stack_
- But this _**Event Listener**_ will stay over here in the _**Web API environmnet**_ until and unless we explicitly **_remove_** that Event Listener or we like **_close the browser_**
- So this registered callback method inisde the Web API environment just sits over there in the hope that some user will someday click on the button.
- When the user clicks on the button, is then pushed inside the **_Callback Queue_** and Callback method (cb()) goes in the _**Callback Queue**_ and waits overe here for its turn to get executed

### _More about EVENT LOOP_

![2 - i event loop   callback after execution](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/dfe6b8bd-ca0f-438a-b4fb-847c991b4566)

![Event Listener after Execution once without callback executing - 3](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/cba9cb8f-2ac0-42ea-b5ca-65f83b304581)


- Event Loop has just one job
- It's only job is to like continuously **monitor** the _**Call Stack**_ as well as the _**Callback Queue**_
- If the Call Stack is empty and this Event loop sees that there is also a function waiting to be executed in the Callback Queue.
- So Event Loop just takes the function and pushes indise the _Call Stack._ And the callback method is like quickly executed then.
- So now the callback method runs the code line by line, and just sees the **`console.log("Callback");`** , it prints this callback inside the console
- When the `Event Loop` picks the _**callback**_ from the callback queue, it then **_removes_** from the _Callback Queue_

## _Why do we need Event Loop_
- Suppose user clicks on a button 7-8 times continuously, it that case the callabck will be pushed inside Callback Queue for 7-8 times.
- There will be 7-8 Callback functions waiting to get executed inside this _**Callback Queue**_
= We will have a queue of Callback functions waiting to be executed
- And Event Loop will continuously check whether the Call Stack is empty or not. And if the Call Stack is _**Empty**_ and there is some function lined up to be executed in the Callback Queue. So _**Event Loop**_ takes that function and put it inside the **_Call Stack_**
- And Slowly slowly, the **_Callback function_** pops off from the _**Callback Queue**_ 


![callback queue](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/ba23080f-a430-454b-8631-40b9e3ce9435)

## _How fetch() function works_
- 








































































