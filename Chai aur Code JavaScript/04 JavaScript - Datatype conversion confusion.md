## _Lecture 6 - Datatype conversion confusion | Chai aur JavaScript_

<b>

```js
let score = 33
console.log(typeof score);   //number
console.log(typeof(score));  //number
//Above both ways are different types of writing typeof

let marks="90"
console.log(typeof marks);  //string
console.log(typeof(marks)); //string

let valueInNumber = Number(marks);
console.log(typeof valueInNumber);  //number 
console.log(vaueInNumber); //NaN

let notANumber="23cc"
console.log(typeof notanumber); //NaN - Not A Number

let isLoggedIn = 1
let booleanIsLoggedIn = Boolean(isLoggedIn)
console.log(booleanIsLoggedIn); // true

let isLoggedIn = 0
let booleanIsLoggedIn = Boolean(isLoggedIn)
console.log(booleanIsLoggedIn); // false

let isLoggedIn = "anupam"
let booleanIsLoggedIn = Boolean(isLoggedIn)
console.log(booleanIsLoggedIn); // true

let isLoggedIn = ""
let booleanIsLoggedIn = Boolean(isLoggedIn)
console.log(booleanIsLoggedIn); // false

// Notes
// "33" => 33
// "33abc" => NaN
// true => 1; 
// false => 0;
// "" => false  - empty string
// "anupam" => true - string with some value in it

let someNumber = 33;
let stringNumber = String(someNumber)
console.log(stringNumber); // 33
console.log(typeof stringNumber); // string
```
</b>



