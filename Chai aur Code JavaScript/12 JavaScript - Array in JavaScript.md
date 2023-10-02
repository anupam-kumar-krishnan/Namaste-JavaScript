## _14 Lecture - Array in JavaScript_

### _Shallow Copy_
A Shallow copy of an object is a copy whose properties share the same reference point as those of the source 
object from which the copy was made.

### _Deep Copy_
A Deep Copy of an object is a copy whose properties do not share the same reference as those of the source object from
which the copy was made


<b>

```js
// array
const myArr = [0, 1, 2, 3, 4, 5];
console.log(myArr[0]); // 0
console.log(myArr[1]); // 1

const myHeros = ["shatiman", "nagraj"];

const myArr2 = new Array(1, 2, 3, 4);

// Array methods
// push: adds at the end
myArr.push(6);
console.log(myArr); // [0, 1, 2, 3, 4, 5, 6]

// pop: removes from the end
myArr.pop();
console.log(myArr); // [0, 1, 2, 3, 4, 5]

// unshift: adds at the start
myArr.unshift(10);
console.log(myArr); // [10, 0, 1, 2, 3, 4, 5]

// shift: removes from the start
myArr.shift();
console.log(myArr); // [0, 1, 2, 3, 4, 5]

// includes
console.log(myArr.includes(9)); // false

// indexOf
console.log(myArr.indexOf(9)); // -1

const newArr = myArr.join();

console.log(myArr); // [0, 1, 2, 3, 4, 5]
console.log(typeof newArr); // string

// slice, splice

console.log("A ", myArr); // [0, 1, 2, 3, 4, 5]

// slice
const myn1 = myArr.slice(1, 3);
console.log(myn1); // [1, 2]
console.log("B ", myArr); // [1, 2, 3, 4, 5]
// In Slice, the "Original Array" remains the same.

// splice
const myn2 = myArr.splice(1, 3);
console.log(myn2); // [1, 2, 3]
console.log("C ", myArr); // [0, 4, 5]
// In Splice, the "Original Array" got changed.

// Arrays are not associative array and so, array elements cannot be accessed using nonnegative integer
// JavaScript arrays are zero-indexed
// JavaScript array-copy operations create shallow copies
```
</b>


