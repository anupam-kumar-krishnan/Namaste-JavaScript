# _JS Engine_
- JavaScript can run inside a browser, server, smart watch, robot
- It's all possible because of JavaScript Runtime Environment

## _JavaScript Runtime Environment_

![JS Runtime Environment](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/04f66b20-732d-444c-9714-1e38cf5b35b8)


- **_JavaScript Runtime Environment_** is like a big container which has all the things required to run JavaScript code
- **_Browser_** can only execute the JavaScript Code just because it has the _**JavaScript Runtime Environment**_
- Every **_Browser_** has **_JavaScript Runtime Environment_**
- **_JavaScript Runtime Environment_** is not possible without the _**JavaScript Engine**_ i.e. **_JavaScript Engine_** is the heart of **_JavaScript Runtime Environment_** 

- **_Node JS_** also has a **_JavaScript Runtime Environment._** Node JS has everything which is required to run a JavaScript piece of code
- And _**Node JS**_ can run this piece of code **_Outside the Browser_**

- The **_APIs_** are different in case of **_Browsers_** and **_Node JS._** Sometimes it can be common also.
- Suppose Browser has an **_API_** known as **_`LocalStorage`_** that gives us super power of **accessing** **_`LocalStorage`_** from our code.
- And in Case of **_Node JS,_** it could be different
- And there are few APIs which have the same name in **_`Browsers`_** as well as **_`Node JS`_** For example, **_setTimeout()_** i.e. setTimeout is present in the **_Runtime Environment of the Browsers_** as well as in **_Node JS_**
- Same is the case with console. 
- So, these APIs name looks same. But _**internally they are implemented very differently inside**_

## _List of JS Engines_
- All browsers have their own **_JavaScript Engine_**
- **_Microsoft Edge_** : **_`Chakra`_**
- **_Mozilla Firefox_** : **_`SpiderMonkey`_**
- **_Google Chrome_** : **_`V8`_**
<br>

- You can also make your own JavaScript Engine
- The most important protocol is following the standards. There are **_ECMAScript Standards_** which needs to be followed by these **_Engines_**
- **_ECMAScript_** like the **_governing body_** of the **_JavaScript Language_**
- _**`First JavaScript Engine`**_ was developed by the creator of JavaScript himself i.e. **_`Brendan Eich`_**
- He created **_JavaScript_** and he also created _**`JavaScript Engine`**_ when he was working in _**Netscape**_

### _Myths about JS Engine_
- Note: JS Engine is not a **_`MACHINE.`_**
- JS Engine is like a _**normal program**_ which is written in **_`Low Level Languages`_**
- For example, **_Google's V8 Engine_** is written in `C++`
- That JS Engine take the _**High Level Code**_ which we write and spits the **_Machine Code_** which can be _**executed**_ by the Machine

## _JavaScript Engine's Architechture_

![JS Engine Architecture](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/acad8b9e-dab8-401e-b047-59524a3c87e1)


- JS Engine takes _**Code**_ as an input(the human readable code taht we write in JS)
- _**And this code goes through 3 Major Steps:**_
  - **_Parsing_**
  - **_Compilation_**
  - **_Execution_**
- These are the 3 major things happening with the code inside the JS Engine

### _Parsing_
- During this Parsing Phase, this code is broken down into _**Tokens**_
- And there is also something known as **_Syntax Parser_**
- The job of the _**Syntax Parser**_ is to basically take the code and **_convert_** the code into **_Abstract Syntax Tree(AST)_**

![Abstract Syntax Tree](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/a25a68f3-676d-49d2-9c45-c38cb7e126eb)

- This is the **_Abstract Syntax Tree(AST)_** which is generated after the **_PARSING_** Level.
- Now the **_Abstract Syntax Tree(AST)_** which is generated is passed to the **_COMPILATION_** Phase.
- To View  **_Abstract Syntax Tree(AST)_** of any code visit: **_`astexplorer.net`_**

### _Compilation_
- The **_Compilation_** and **_Execution_** goes hand in hand
- _JavaScript_ has something known as **_Just In Time(JIT) Compilation_** <br>
- Before this, let's see **_Is JavaScript a Interpretted Language or a Compiled Language?_**
  - In many Interpreted languages, the code is executed using a **_`Interpreter`_**
  - This Interpreter basically takes the code & it starts executing the code line by line in the order. 
<br>

- While on the other hand, there are many languages which uses a **_`Compiler`_** to compile their Code
- So in Compiler, your whole code is `Compiled` first of all even before getting `Executed`
- So the `Code` is `Complied` and forms a `New Code` which is the **_Optimised Version_** of the code and then it is **_`Executed`_**

## _Pros & Cons of Interpreter_
- In Interpreter, the code is `FAST`. It Immediately starts executing line by line. It doesn't need to wait for the code to be compiled first and then gets Executed.
- In case of Compiler, we have more `Efficiency`, but in case of Interpreter we have more `Speed`

## _Is JavaScript Interpreted Language or Compiled Language?_
- When JavaScript was initially created by **_`Brendan Eich`_** , it was supposed to be an Interpreted Language. i.e. The JavaScript Engine which he wrote uses a Interpreter to Execute the Code
- Because it used to majorly run on Browsers and Browsers can't wait for that code to Compile before running or executing everything
- So it was an `Interpretor Language`

- But now, today you see most of the modern browsers you see and most of the modern JavaScript Engines uses an **`Interpreter`** plus(+) a **`Compiler`** both
- So now, it all depends on the JS Engine whether it is purely Interpreted or Just In Time(JIT) Compiled

## _JIT Compilation_
- JIT Compilation is like the best of the both Worlds
- It uses both **`Interpreter`** plus(+) a **`Compiler`** to execute the code
- So now, `Compilation` + `Execution` both goes hand in hand
- After **_Parsing_** we got this _Abstract Syntax Tree(AST)_ , so this AST goes to the **_`Interpreter`_**
- So now this **_`Interpreter`_** converts our **_High Level Code_** to **_Byte Code_** and that code moves to the **_`Execution Step`_**
- And while it is doing so, it takes the help of the _**`Compiler`**_ to **_Optimise the Code_**
- So when **_Compiler_** talks to the **_Interpretter_** and while the code is executing line by line, the _Compiler also tries to Optimise the Code as much as it can on the runtime._
- It is not just one Phase process, but it can happen in multiple phases
- In some JavaScript Engines, there is something known as **_Ahead of Time(AOT)._** In that case, the compiler basically takes the piece of code which is going to be executed later and tries to Optimise it as much as it can.
- And it also produces the byte code which is then goes to the **_`Execution Phase`_**
<br>

- And the _**Execution**_ here is not possible without the two major Componenets of the **_JavaScript Engine_**.
- Those 2 components are the **_Memeory Heap_** & the **_Call Stack_**
- **_Mememory Heap_** is the space where all the **_variables & functions_** are assigned **_Memory_** 

## _Garbage Collector_
- We also have Garbage Collector, it basically tries to free up **_Memory Space_** whenever possible
- Whenever some function is not being used or we clear the timeout. So basiccaly it collects all the **_garbage_** and sweeps it
- So, it uses an algorithm which is known as **_Mark & Sweep Algorithm_** 

### _There are many other forms of optimisations which a compiler does for the code_
**_And those optimisations are like:_**
- Inlining
- Copyalision
- Inline Caching

## _Fastest JavaScript Engine - Google v8_

![v8 Engine](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/4386a377-1a88-4921-b808-f0e1bd3b1db8)

- The fastest JavaScript Engine ever created is Google's v8 Engine
- v8 has an _Interpretter_ which is known as **_Ignition_**
- Along with that we have _**Turbo Fan,**_ the _Optimising Compiler_
- These **_Ignition_** & **_Turbo Fan_** is making the code run very **_Fast_**
- It also has a _Garbage Collector_ known as **_Orinoco._**
- It uses the **_Mark & Sweep Algorithm_**
























































































