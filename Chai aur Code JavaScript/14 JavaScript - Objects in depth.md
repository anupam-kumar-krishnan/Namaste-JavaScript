## _Lecture 16 - Objects in depth in Javascript_

**_Two ways to define an object:_**
- Literal
- Constructor

### _Singleton_
- Whenever object defined as **_constructor_**, _**singleton**_ object is made
- Whenever object defined as **literal**, singleton object is not made

### _Object_
- In Object, there is concept of _**keys & values**_
- By default, name is considered as "name" by system but not written in real

<b>

```js
// Singlton
// Object.create - this is constructor method, and singleton is made in this

// Object Literals
const JsUser = {
    name: "Hitesh",
    "full name" : "Hitesh Choudhary",
    age: 18,
    location: "Jaipur",
    email: "hitesh@google.com",
    isLoggedIn: false,
    lastLoginDays: ["Monday", "Saturday"]
}

//Wrong way of accessing Objects
console.log(JsUser.email); // hitesh@google.com

//Correct way of accessing Object
console.log(JsUser["email"]) // hitesh@google.com

// **Note**
// if key value is given in strings like full name above then, 
// there is no chance that we can access it by using dot

console.log(JsUser["full name"]); // Hitesh Choudhary

console.log(JsUser.full name); // this will throw error, also we can write full name in invited commas as it is not allowed 
```

### _Add a symbol as key in an object_
```js
// declare a symbol
const mySym = Symbol("key1")

const JsUser = {
    name: "Hitesh",
    "full name" : "Hitesh Choudhary",
    mySym: "mykey1",
    age: 18,
    location: "Jaipur",
    email: "hitesh@google.com",
    isLoggedIn: false,
    lastLoginDays: ["Monday", "Saturday"]
}

console.log(JsUser.mySym); // mykey1
console.log(typeof JsUser.mySym); // string

// to get mySym as symbol, write mySym in square backet like
const JsUser = {
  name: "Hitesh",
  "full name": "Hitesh Choudhary",
  [mySym]: "mykey1",
  age: 18,
  location: "Jaipur",
  email: "hitesh@google.com",
  isLoggedIn: false,
  lastLoginDays: ["Monday", "Saturday"],
};

console.log(JsUser.email); // mykey1

/************************NOTE**************************
there is no change in value but, in interviews
correct Syntax of Symbol: const mySym = Symbol("key1")
Treat Symbol like Value: [mySym]: "mykey1"
*******************************************************/
```


## _To freeze a Object_

```js
// declare a symbol
const mySym = Symbol("key1");

const JsUser = {
  name: "Hitesh",
  "full name": "Hitesh Choudhary",
  [mySym]: "mykey1",
  age: 18,
  location: "Jaipur",
  email: "hitesh@google.com",
  isLoggedIn: false,
  lastLoginDays: ["Monday", "Saturday"],
};

JsUser.email = "hitesh@chatgpt.com";
Object.freeze(JsUser);
JsUser.email = "hitesh@microsoft.com";
console.log(JsUser);

/* Output
{
  name: 'Hitesh',
  'full name': 'Hitesh Choudhary',
  age: 18,
  location: 'Jaipur',
  email: 'hitesh@chatgpt.com',
  isLoggedIn: false,
  lastLoginDays: [ 'Monday', 'Saturday' ],
  [Symbol(key1)]: 'mykey1'
}
*/
// Email didn't change after hitesh@chatgpt.com
// as it is freezed after hitesh@chatgpt.com

/******************************NOTE************************************
- To refer Symbol: Use Square Brackets
  i.e. [mySym]: "mykey1"

- To refer as key Value Pair: Write as it is, without square bracket
  i.e. mySym: "mykey1"
************************************************************************/
```

## _Add Function_
- From `12:43` Video 15



</b>
