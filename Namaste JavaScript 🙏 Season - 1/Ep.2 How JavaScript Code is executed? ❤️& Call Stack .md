## _What happens when you run JavaScript code?_
- An **`Execution Context`** is **_created_**

### _Execution Context is created in Two phases:_

 _**1. Memory Creation Phase:**_ In this phase, JavaScript runs through the program & allocates memory to all variables & functions. JavaScript swims throughout the whole code and allocate a special value **`undefined`**<br>
 _**2. Code Execution Phase:**_ In this phase, each line is executed line by line


Let's take an example:

![Phase 1](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/78ce6962-5167-4c4d-b9ef-5d5b4dbc8991)
![2](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/39dcc91b-d470-4dfa-8694-f9f3bc555574)
![3](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/5bc0803a-f063-4aea-9781-b3d46443001b)
![4](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/b41d459d-662d-4988-a411-63c09bfb8ddd)
![5](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/ea3b571b-34f3-420f-8fe7-f96e6f1fd5e6)

- Once JavaScript is done with all it's work, the program is finished.
- Now, the whole **`Global Execution Context`** also gets deleted
- This is too much for JavaScript Engine to handle.  To handle this creation & deletion of Execution Context, it manages a stack known as **_Call Stack_**

## _Call Stack_
- Everytime, at the bottom of the stack, we have our `Global Execution Context`
- Whenever any Javascript code is run, this call stack is populated with the Global Execution Context
- Whenever a new Execution Context is created, it is pushed inside the stack

### _Call stack maintains the order of execution of execution contexts_

<img width="1133" height="593" alt="image" src="https://github.com/user-attachments/assets/5ca5cf8a-8790-4eba-9752-5d4fb8cb2b2e" />


## _Call stack is also known by below names_
_**0. Call Stack**_ <br>
_**1. Execution Context Stack**_ <br>
_**2. Program Stack**_ <br>
_**3. Control Stack**_ <br>
_**4. Runtime Stack**_ <br>
_**5. Machine Stack**_ <br>




