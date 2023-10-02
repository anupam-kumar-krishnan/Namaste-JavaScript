# _JavaScript_
## _What the whole thing is about: Data_
- To store any data we need some memory where we can store

## _let, const and var_
- **_const:_** once value is assigned, cannot be changed further<br>
example: const pi=3.14;
- **_var:_** Prefer not to use **var**, because of issue in **block scope** and **functional scope**
- Use const & let
- In JavaScript, there is a possibility, that we can declare a variable without even using let and var(but it is not prefered)

## _undefined_
- In JavaScript, if we decalre a variable without assigning a value to it, then it is called **_undefined_**

<b>


```javascript
const accountId = 214512;
let accountEmail = "anupam@gmail.com";
var accountPassword = "12345";  // it has scope
accountCity = "Pune";
let accountState;

//accountId = 5; // not allowed

accountEmail = "b@gmail.com";
accountPassword = "21245";
accountCity = "Bengaluru";

console.log(accountId);

// Prefer not to use var because of issue in block scope and functional scope

console.table([
    accountId,
    accountEmail,
    accountPassword,
    accountCity,
    accountState
]);
```
</b>


### _Output_
```
┌─────────┬───────────────┐
│ (index) │    Values     │
├─────────┼───────────────┤
│    0    │    214512     │
│    1    │ 'b@gmail.com' │
│    2    │    '21245'    │
│    3    │  'Bengaluru'  │
│    4    │   undefined   │
└─────────┴───────────────┘
```








