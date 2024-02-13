## _map, filter & reduce_
- map(), filter() and reduce() are Higher-Order functions in JavaScript

### _map()_
- map function is basically used to transform an array

<b>

```js
const arr = [5, 1, 3, 2, 6];

// Double - [10, 2, 6, 4, 12]

// Triple - [15, 3, 9, 6, 18]

// Binary - ["101", "1", "11", "10", "110"]

function double(x){
    return x * 2;
}

function triple(x){
    return x * 3;
}

function binary(x){
    return x.toString(2);
}

const output = arr.map(double);
console.log(output);
// [10, 2, 6, 4, 12]

const toutput = arr.map(triple);
console.log(toutput); 
// [15, 3, 9, 6, 18]

const boutput = arr.map(binary);
console.log(boutput);
// ['101', '1', '11', '10', '110']
```

```js
const arr = [5, 1, 3, 2, 6];

const boutput = arr.map(function binary(x) {
    return x.toString(2);
});

const output = arr.map((x) => x.toString(2));
```
</b>

## _Array.filter() function in JavaScript_
- filter function is actually used to `filter`
- filter function is actually used to `filter` the value inside an array

<b>

```js
const arr = [5, 1, 3, 2, 6];

// filter odd values
function isOdd(x){
  return x % 2;
}

const outputOdd = arr.filter(isOdd)
console.log(outputOdd);
// [5, 1, 3]

//filter even values
function isEven(x){
  if(x%2==0)
    return x;
}

const outputEven = arr.filter(isEven)
console.log(outputEven);
// [2, 6]
```
</b>

## _Array.reduce() function in JavaScript_
- As the name suggests reduce, but it actually **_doesn't reduce anything_**
- It used where you have to take the values of an array and comeup with a single value out of them

<b>

```js
const arr = [5, 1, 3, 2, 6];

// sum or max
function findMax(arr){
  let max = 0;
  for(let i = 0; i < arr.length; i++){
     if(arr[i] > max) {
       max = arr[i];
     }
  }
  return max; 
}

console.log(findMax(arr));
// 6

function findSum(arr){
  let sum = 0;
  for(let i = 0; i < arr.length; i++){
     sum = sum + arr[i];
  }
  return sum;
}

console.log(findSum(arr));
// 17

const output = arr.reduce(function(acc, curr){
  acc = acc + curr;
  return acc;
}, 0);

console.log(output);
// 17

const outputUsingReduce = arr.reduce(function (max, curr){
    if(curr > max) {
    max = curr;
    } 
   return max;
}, 0);

console.log(outputUsingReduce);
// 6

// acc - accumulator - used to accumulate the result what we get out of those values which are present in the array
// curr - current - represents the values inside the reduce function
// here acc is behaving like the sum variable
// first value is function
// second value is any value which you need to pass to the acc
```
## _Real World Example_

```js
const users = [
 { firstName: "akshay", lastName: "saini", age: 26 },
 { firstName: "donald", lastName: "trump", age: 75 },
 { firstName: "elon", lastName: "musk", age: 50 },
 { firstName: "deepika", lastName: "padukone", age: 26 },
];

// list of full names
// ["akshay saini", "donald trump", "elon musk", "deepika padukone"]

const output = users.map(x => x.firstName + " " + x.lastName)
console.log(output);
//  ['akshay saini', 'donald trump', 'elon musk', 'deepika padukone']
```

## _Tricky Example - reduce()_

```js
const users = [
 { firstName: "akshay", lastName: "saini", age: 26 },
 { firstName: "donald", lastName: "trump", age: 75 },
 { firstName: "elon", lastName: "musk", age: 50 },
 { firstName: "deepika", lastName: "padukone", age: 26 },
];

// What are different age in this array and how many people are there of this age
// acc = {26 : 2, 75 : 1, 50 : 1}

const output = users.reduce(function(acc, curr){
  if(acc[curr.age]){
  acc[curr.age] = ++acc[curr.age];
  }
  else {
    acc[curr.age] = 1;
  }
 return acc;
}, {});

console.log(output);
// {26: 2, 50: 1, 75: 1}
```

## _Chaining map, filter & reduce_

```js
const users = [
 { firstName: "akshay", lastName: "saini", age: 26 },
 { firstName: "donald", lastName: "trump", age: 75 },
 { firstName: "elon", lastName: "musk", age: 50 },
 { firstName: "deepika", lastName: "padukone", age: 26 },
];

// Find out the firstName of all the people whole age is less than 30
const output = users.filter(x => x.age < 30)
console.log(output);

// Output
// (2) [{…}, {…}]
// 0 : {firstName: 'akshay', lastName: 'saini', age: 26}
// 1 : {firstName: 'deepika', lastName: 'padukone', age: 26}

const outputChanningInMap = 
    users.filter(x =>  x.age < 30)
    .map(x) => x.firstName);

console.log(outputChanningInMap);
// [akshay", "deepika"]
```

</b>








