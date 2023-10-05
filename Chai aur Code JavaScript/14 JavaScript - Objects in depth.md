## _Lecture 16 - Objects in depth in Javascript_

Two ways to define an object:
- Literal
- Constructor

### _Singleton_
Whenever object defined as **constructor**, singleton object is made

<b>

```js
// Singlton
// Object Literals
// Object.create - this is constructor method, and singleton is made in this

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



```


</b>
