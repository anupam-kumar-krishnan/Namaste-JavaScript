# _Promises🤝_
- Promises are used to handle _**Async operations**_ in _**JavaScript**_ <br>
### _**For example, we are creating an e-commerce web app:**_
- So, this cart is nothing but an Array
- These 2 APIs are Asynchronous, we don't know how much time it will take
- Now let's see how will we write using Callbacks
- Callbacks used to be very crucial part while writing Asynchronous Code in our programming
- _**How we handle this type of situation in our code using Callbacks?**_
  - We wrap the function inside a Callback function
  - Now it is the responsibility of createOrder API to create an order firstly and <br>then will call our callback function back once the order is created with the order ID 

<b>

```js
const cart = ["shoes", "pants", "kurta"];

createOrder(cart); //orderId

proceedToPayment(orderId);
```


```js
const cart = ["shoes", "pants", "kurta"];

createOrder(cart, function() {
    proceedToPayment(orderId);
});
```

</b>

- _**But there is a very Important issue with this code**_
  - The _**issue**_ is **_Inversion of Control_**
  - **_What does this mean?_**
  - This means that we have given/passed this Callback function to createOder API and now we are sitting back relax
  - We are relax that at some point of time, this creaeOrder function will just call our Callback function back and everything will be peaceful
  - But, what if we are just blindly trusting this API and it never calls our callback function back or calls twice
  - What we mean to say is, we have given the responsibility of payment `proceedToPayment` to some other APIs and it's not in our control anymore
  - We have just passed in and we are expecting it to be Randomly Magically called when the order is created
  - **_Isn't it Risky?_**
  - So passing callbacks like this isn't reliable, we are just giving control of our program to some other part of our code which we aren't aware of.
  - This is not a very confident way of writing code
  - Let's see how to resole this by using _**Promises**_

## _Promise🤝_
- Promise is nothing but an empty object with some data value in it
- And this dala value will hold whatever this createOrder(cart) API will return to us

<b>

```js
const cart = ["shoes", "pants", "kurta"];

createOrder(cart, function(orderId){
 proceedToPayment(orderId);
});

const promise = createOrder(cart);
// {data: undefined }

// ---- more lines of code
// -----
```
</b>

- Whenever JavaScript Engine will execute this line `const promise = createOrder(cart);` , thsi createOrder API will return us a `Promise` (an empty object)
- And the program will go on executing, suppose there are more lines of code after that
- Then after 5-6 seconds, this Empty Object(Promise) will be filled with data automatically and we will have order details in it after whatever Async time it takes

<b>

```js
const cart = ["shoes", "pants", "kurta"];

createOrder(cart, function(orderId){
 proceedToPayment(orderId);
});

const promise = createOrder(cart);
// {data: orderDetails }
```
</b>

## _Promise.then function_
### _What will happen after getting value in data_
- Now we will attach a callback function to this promise object
- **_How do we do it?_**
   - We will use a function _**`.then`**_
   - `.then` is the function which is available over `Promise` object

<b>

```js
const cart = ["shoes", "pants", "kurta"];

//callback
createOrder(cart, function(orderId){
 proceedToPayment(orderId);
});

//promise
const promise = createOrder(cart);

promise.then(function (orderId) {
  proceedToPayment(orderId);
});
```
</b>

### _What improvement did we make in our code_
- Earlier, we passed the callback function to createOrder API and we were blindly trusing createOrder API, we were relying on it
- And in second case(promise), we are attaching a callback function to a `Promise` object. <br>
  In this case, we will have the control of our program with us.
- How? createOrder API will only do it's job, it will create an order and it will fill the `promise` object with the data(the order ID) wherever it wants to and as soon as this `promise` object is filled with that data, it will automatically call our callback function back
- And we will have the control of our program with us
- And this gives us the trust that promise will call the callback function whenever there is data inside promise object

### _Importance of Promises_ 
- In the earlier piece of code, we had a lot of doubts like what if createOrder function might call our function twice or thrice or it might never call it
- Promises handles it beautifully, as soon as we have data inside `Promise` it will call the function that is the gurantee given by JavaScript and it will call it just once and only once.
- And we will also have the control of our program with us, as we are not passing our code to some other external function

### _Promises Object in Browser_
- If you want to see that object, we will use a function **_`fetch`_**
- _**`fetch()`**_ - An API given by browsers to us to make external calls
- fetch() function returns a **_`Promise`_**

<b>

```js
const GITHUB_API = "https://api.github.com/users/akshaymarch7/"

const user = fetch(GITHUB_API);

/* Scope: 
\/ Script:
     GITHUB_API = "https://api.github.com/users/akshaymarch7/"
\/   user: Promise
       [[Prototype]]: Promise
       [PromiseState]]: "pending"
       [PromiseResult]]: undefined
```
</b>

- As soon as the line of code is executed, we will get a **_`Promise`_** object inside this user 
- So right now, this `Promise` is in a `pending` State
- **_`PromiseResult:`_** it will store whatever data that fetch() will return
- **_`PromiseState`_** : in what state your **_`Promise`_** is. Initially, the promise will be in pending state and once we got the data back, the promise state will chage to **_`fullfilled`_** state

### _Deep dive into Promise States_

<b>

```js
const GITHUB_API = "https://api.github.com/users/akshaymarch7/"

const user = fetch(GITHUB_API);

console.log(user);

// Promise{<pending>}
```
</b>





 


































