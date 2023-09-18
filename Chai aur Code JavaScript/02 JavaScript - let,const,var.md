# _JavaScript_
## _let, cont and var_
- Prefer not to use **var**, because of issue in **block scope** and **functional scope**
- In JavaScript, there is a possibility, that we can declare a variable wiouth even using let and var(but it is not prefered)

## _undefined_
- In JacaScript, if we decalre a variable without assigning a value to it, then it is called **_undefined_**

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

console.table([accountId, accountEmail, accountPassword, accountCity]);
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








