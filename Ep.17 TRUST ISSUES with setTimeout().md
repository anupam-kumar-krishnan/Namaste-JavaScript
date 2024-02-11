# _TRUST ISSUES 💔 with setTimeout()_

- A **_`setTimeout`_** with a delay of **5000ms** _doesn't always exactly wait_ for **5s**
- There are **_Trust Issues_**
- **_`setTimeout`_** doesn't gurantee that the Callback method will be exactly after 5s. It might take 6s or may be 10s
- This all depends on the _**Call Stack**_ <br><br>
- **_Let's try to Understand with an example:_**
- What happens when you run a JavaScript Code, a **_Global Execution Context_** is created and **pushed** inside the **_Call Stack_**
- Now, the code will run line by line
- The first line, **_`console.log("Start")`_**, this will print **_Start_** in the **conosle** using the **_console of Web API_**









