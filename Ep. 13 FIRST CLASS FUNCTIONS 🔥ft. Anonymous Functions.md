# _Diving Deeeeeep into Functions_

_**- What is an Anonymous Funtion?**_ <br>
_**- What are First Class Functions in JavaScript?**_ <br>
_**- Function Statement vs. Function Expression vs. Function Declaration?**_


### _Function Statement_
- This way of creating a function is known as **_`Function Statement`_**
- Function Satement is also known as **_`Function Declaration`_**

<b>

```js
function a(){
 console.log("a called");
}
```
</b>

### _Function Expression_
- You can assign function to a variable also

<b>

```js
var b = function() {
  console.log("b called");
}
```
</b>

### _Difference b/w Function Statement & Function Exression_
- The major difference between these two is **_`Hoisting`_**

<b>

```js
a();
b();

//Function Statement
function a() {
  console.log("a called");
}

//Function Expression
var b = function() {
   console.log("b called");
}

// Output
// a called
// UnCaught TypeError: b is not a function


```
</b>

### _Anonymous Function_
- A function without a name is called **_`Anonymous Function`_**
- Anonymous Functions doesn't have it's own identity
- By doesn't not have it's own identity means if you create a anonymous function, this will result out to be a Syntax Error
- An Anonymous function looks like a `Function Statement`, but it has _**no name**_. But according to ECMAScript specification, _**a Function Statement should always have a name**_
- This is an invalid Syntax.
- Results in `UnCaught SyntaxError: Function statements require a function name`   
- _**Anonymous Functions**_ are used in a place **_where functions are used as values_**

<b>

```js
function () {

}
```
</b>

### _Named Function Expression_
- A Named Function Expression is exactly the same as Function Expression but instead of using an Anonymous Function, we use a Function with a name
- Have a name of a Function itself and put it into an Expression

<b>

```js
var b = function xyz(){
  console.log("Named Function Expression");
}

b();
```
</b>

### _Corner Case Gotcha using Named Function Expression_
- In this case, xyz() is not a function inside the outer scope(Gobal Scope)
- But it(xyz()) is created as a **_local variable_** 

<b>

```js
function a(){
  console.log("a called");
}

var b = function xyz(){
  console.log("Named Function Expression");
}
a(); // a called
xyz(); // Uncaught ReferenceError: xyz is not defined
```
</b>

- You can access like this below:

<b>

```js
var b = function xyz(){
    console.log(xyz);
}
```
</b>














