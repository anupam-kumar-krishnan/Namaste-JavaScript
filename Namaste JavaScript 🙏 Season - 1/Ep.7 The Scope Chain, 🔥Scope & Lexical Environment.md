## _Scope_

### _Can we access b inside function a()_
- JavaScript will try to find out weather b exists in the local memory space or not 
- JavaScript will try to find out this b inside a's Execution Context, but it will not be found as we never created b inside that function
- Now what will happen? Will it print **`undefined`**- that special placeholder or **`not defined`**?
- This print 10 as an output, that means somehow inside the function, this `b` can _**access**_ the `b` which is _**outside the function**_ 

<b>

```js
function a() {
 console.log(b);
}
var b = 10;
a();

// Output
// 10
```
</b>

![scope 1](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/e08879b0-04d1-4ad9-a98d-f671ac1f96cb)


### _Can I access b now?_
- Yes, still I can access `b`
- Even inside the function(c), which is inside another function(a), which is inside the Global Scope, I can access `b`

<b>

```js
function a() {
  c();
  function c(){
    console.log(b);
  }
}

var b = 10;
a();

// Output
// 10
```

</b>

### _Can I access b outside the function_

<b>

```js
function a(){
   var b=10;
   c();
   function c(){
 
   }
}

a();
console.log(b);

// Output
// b is not defined
```
</b>

## _Scope_
- Scope means where you can access a specific variable or a function in our code
- _**Scope**_ is _**directly**_ dependent on the **`Lexical Environment`**

_**There are 2 ways to look at this:**_
- Where can I access this variable b(What is the scope of variable b, here in example)
- Is b inside the scope of function c(Can I access b inside c)

## _Lexical Environment_
- Whenever an **_Execution Context_** is created, a **_Lexical Environment_** is also created
- _**Lexical Environment**_ is the _**Local Memeory**_ along with the _**Lexical Environment of it's Parent**_
- _**`Lexical Environment`**_ = _**`Local Memory`**_ + _**`Lexical Environment of it's Parent`**_

![Lexical Environment Visual Representation](https://github.com/anupam-kumar-krishnan/Namaste-JavaScript/assets/69143883/8868a329-70ec-4ead-9f44-d44551c48095)

## _What is Lexical_
- Lexical as a term means in _**hierarchy**_ or in a _**sequence**_
- c() is lexically sitting inside a()
- Where the code is physically present
- Lexical Parent of c is a (because c is lexically inside a, that means it will get access of  lexical environment of a also)
- Lexical Parent of a is null as a is in Global Execution Context whose Parent is null


## _How Scope and Lexical Environment works in JavaScript_

<b>

```js
function a(){
  var b = 10;
  c();
  function c(){
   console.log(b);
  }
}

a(); //10
console.log(b); //10
```

</b>


- It is tries to find b in local memeory of c
- First it check if b exits in local memory or not
- It won't find, because there is no b inside this local memory

- Now, what happens JavaScript Engine goes to the reference and goes to the lexical environment of it's parent which is `a` in this case
- This time, it finds `b` in `a()`(Lexical Environment of c)
- It goes back in function `c()` and prints the value of `b` in console



## _Scope Chain_
- Scope Chain is nothing but the `Chain of Lexical Environment` and the `Parent references`
- Scope chains establish the scope for a given function. Each function defined has its own nested scope, and any function defined within another function has a local scope which is linked to the outer function — this link is called the _**chain.**_









