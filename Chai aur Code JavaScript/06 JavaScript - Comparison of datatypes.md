## _Comparison of datatypes in JavaScript_

<b>


```js
console.log(2 > 1); //true
console.log(2 >= 1); //true
console.log("2" >= 1); // true
console.log("02" >= 1); //true

//null comparison
console.log(null > 0); //false
console.log(null == 0); //false
console.log(null >= 0); //true

//undefined comparison
console.log(undefined == 0); //false
console.log(undefined > 0);  //false
console.log(undefined < 0);  //false

// Please avoid writing above null and undefined comparison

// strict check i.e. ===(triple equals)
// strict check not only checks value but also datatype
console.log("2" === 2); //false | different datatypes

/*The reason is that an equality check == and 
comparisons > < >= <= work differently.'
Comparisons convert null to a number, treating it as 0.
That's why null >= 0 is true and null > 0 is false.*/
```
</b>
