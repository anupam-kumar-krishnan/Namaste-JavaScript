## _Datatype conversion confusion_
<b>

```js
let score = 33
console.log(typeof(score));  //number
console.log(typeof(score));  //number

let marks="90"
console.log(typeof marks);  //string
console.log(typeof(marks)); //string

let valueInNumber = Number(marks);
console.log(typeof valueInNumber);  //number 

let notANumber="23cc"
console.log(typeof notanumber); //NaN - Not A Number

let isLoggedIn = ""
let booleanIsLoggedIn = Boolean(isLoggedIn)
console.log(booleanIsLoggedIn); // false

let isLoggedIn = "anupam"
let booleanIsLoggedIn = Boolean(isLoggedIn)
console.log(booleanIsLoggedIn); // true

// 1 => true; 
// 0 => false;
// "" => false  - empty string
// "anupam" => true - string with some value in it

let someNumber = 33;
let stringNumber = String(someNumber)
console.log(stringNumber); // 33
console.log(typeof stringNumber); // string
```
</b>



