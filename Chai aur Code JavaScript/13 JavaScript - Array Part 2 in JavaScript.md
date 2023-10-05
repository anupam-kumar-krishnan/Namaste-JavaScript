## _Lecture 15 - Array in JavaScript Part 2_
<b>

```js
const marvel_heros = ["Thor", "Ironman", "Spiderman"]
const dc_heros = ["Superman", "Flash", "Batman"]

marvel_heros.push(dc_heros); // this way is not preferred

console.log(marvel_heros);
// [ 'Thor', 'Ironman', 'Spiderman', [ 'Superman', 'Flash', 'Batman' ] ]
// Just to prove the fact that aaray can take any data, it took "dc_heros" as one data 

console.log(marvel_heros[3][1]); // flash | this way is not preferred
// accessing in this way is not preferred
```

### _Better way is to concatenate:_

```js
const marvel_heros = ["Thor", "Ironman", "Spiderman"];
const dc_heros = ["Superman", "Flash", "Batman"];

marvel_heros.concat(dc_heros);
// the above concatenation is also not working properly as the ouput should contain every element of marvel_heros as well as dc_heros

console.log(marvel_heros);
//[ 'Thor', 'Ironman', 'Spiderman']
```

### _The right way to concatenate:_

```js
const marvel_heros = ["Thor", "Ironman", "Spiderman"];
const dc_heros = ["Superman", "Flash", "Batman"];

const allHeros = marvel_heros.concat(dc_heros);

console.log(allHeros);
//[ 'Thor', 'Ironman', 'Spiderman', 'Superman', 'Flash', 'Batman' ]
```

## _Spread Operator_
- There is a cup made of glass, it will spread when it drops
- It Spreads, will be shattered into pieces
- Best way to concatenate


```js
const marvel_heros = ["Thor", "Ironman", "Spiderman"];
const dc_heros = ["Superman", "Flash", "Batman"];

const all_new_heros = [...marvel_heros, ...dc_heros];
console.log(all_new_heros);
//[ 'Thor', 'Ironman', 'Spiderman', 'Superman', 'Flash', 'Batman' ]
```

## _Flat_
- Returns a new array with all sub-array elements concatenated into it recursively up to the specified depth. 

```js
const another_array = [1,2,3,[4,5,6],7,[6,7,[4,5]]]

const real_another_array = another_array.flat(Infinity); 
// Instead of Infinity : actual, count of real number of arrays presented inside one another should be entered
console.log(real_another_array);


/* Output
[
  1, 2, 3, 4, 5,
  6, 7, 6, 7, 4,
  5
]
*/
```

## _Check if one is array or not: isArray_

```js
console.log(Array.isArray("Hitesh")); // false
```

## _Convert a String to an array: from_
```js
console.log(Array.from("Hitesh"));
// ["H","i","t","e","s","h"]

console.log(Array.from({name: "Hitesh"}));
// []
// made from key value pair
```

## _Convert Values to Array_

```js
let score1 = 100
let score2 = 200
let score3 = 300
console.log(Array.of(score1, score2, score3));
// [ 100, 200, 300 ]
```

### _Study a bit about_
 - isArray
 - from
 - of



</b>

