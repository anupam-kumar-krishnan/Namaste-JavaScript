# _Callback Hell_
### _Good Parts_
- How callbacks are _**super powerful**_ way of handeling _**Asynchronous Operatins/Code in JavaScript**_
- In fact, **_Async Programming_** in JavaScript exists because _**Callabck exists**_


### _Bad Parts_
- Using Callbacks can let us face issues.
- _**There are 2 major issues while writing Callback:**_
  1.  _**Callback Hell**_
  2. _**Inversion of Control**_
- These 2 issues will help in understanding **_Promises_** very well.

<b>

```js
console.log("Namaste");

console.log("JavaScript");

console.log("Season 2");
```
</b>

## _Callback Hell_
- Below code is an example of **_Callback Hell_**
- The below structure is known as **_Pyramid of DOOM_**

<b>

```js
const cart = ["shoes", "pants", "kurta"];

api.createOrder(cart, function() {

    api.proceedToPayment(function () {

        api.showOrderSummary(
         
             function() {
                 api.updateWallet()
             }

        )

    })

})
```
</b>

## _Inversion of Control_
- It is the another problem we see while using Callbacks
- _**Inversion Of Control**_ is like you **_loss the control of your code_** when we are using **_Callbacks_**
- Whenever we have this Callback function and we pass it into another function, we are giving the control of our function(our piece of wriiten code) to some other code
- And we **_don't know what's happening behind the scenes_**
- This is a very important problem that we face when we are using _**Callbacks**_

<b>

```js
const cart = ["shoes", "pants", "kurta"];

api.createOrder(cart, function() {

   api.proceedToPayment()

})
```
</b>









