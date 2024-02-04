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
   - If you give a script and say that execute it 5seconds later then it cannot do that because it(call stack) doesn't not a timer.
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























