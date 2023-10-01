### _Lecture 7 - Why String to Number is Confusing | Chai aur Code_ 
## _Operations_
<b>

```js
let value = 3;
let negValue = -value;
console.log(negValue); // -3
```

```js
let str1 = "Hello"
let str2 = "Hitesh"
let str3 = str1 + " " + str2;

console.log(str3); // Hello Hitesh

console.log("1" + 2); // 12
console.log(1 + "2"); // 12
console.log("1" + 2 + 2) // 122 
// if first i string then rest all will be treated as string
console.log(1 + 2 + "2") // 32

console.log(true); // true
console.log(+true); // 1
console.log(true+); // Syntax error: Unexpected token ')'
console.log(+""); // 0
```

## _Prefix and Postfix_

```js
let gameCounter = 100
gameCounter++;
console.log(gameCounter); // 101

let gameCounter = 100
++gameCounter;
console.log(gameCounter); // 101

```

</b>


