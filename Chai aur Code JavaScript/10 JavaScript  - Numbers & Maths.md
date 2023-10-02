## _Lecture 12 - Numbers & Maths in JavaScript_

<b>

### _Numbers_


```js
const score = 400
console.log(score); //400

const balance = new Number(100) //object
console.log(balance); //[Number: 100]
// Here, numbers is printed as ouput
// Here, Type: Number
// new Number defined object which is Number in type

//toString
console.log(balance.toString()); //100 (but now the datatype of balance is 'String')
console.log(typeof balance); //object
console.log(balance.toString().length); //3
console.log(balance.toFixed(2)); //100.00

//toPrecision
const otherNumber = 23.8966
console.log(otherNumber.toPrecision(3)); //23.9

const otherNewNumber = 123.8966
console.log(otherNewNumber.toPrecision(2)); //124

//toLocaleString
const hundreds = 1000000
console.log(hundreds.toLocaleString()); //1,000,000 (this gives in US standards)

const indianHundred = 1000000
console.log(indianHundred.toLocaleString('en-IN')); //10,00,000 (Indian Standards)

```

## _Maths Library_


### _Math: an object_

```js
console.log(Math); //Object [Math] {}

// abs() Absolute Value: negative value becomes positive
console.log(Math.abs(-4)); //4

// round()
console.log(Math.round(4.6)); //5
console.log(Math.round(4.3)); //4

// ceil() Always selects top value
console.log(Math.ceil(4.2)); //5

// floor Always selects lower value
console.log(Math.floor(4.2)); //4
console.log(Math.round(4.9)); //4

// min() and max()
console.log(Math.min(4, 3, 6, 8)); //3
console.log(Math.max(4, 3, 6, 8)); //8

// random() Value always comes between 0 to 1
console.log(Math.random()); //0.289215686067837

// While making dice game
console.log(Math.random()*10 + 1); //7.68842426709209

// Here, by multiplying random by 10, we get once number before decimal
// And by adding one(1) to it, makes sure that output never comes to be zero,
// as the result of random() can be zero, 
// and multiplying 10 to it will doesn't make any difference i.e. zero(0)
// Hence, minimum value is now one(1)

console.log(Math.random()*10 + 1);


//To make above optimize w.r.t BODMAS rule, close in brackets
console.log((Math.random()*10) + 1); //7.68842426709209

// Another way, use floor for getting single digit output(values b/w 1 to 9)
console.log(Math.floor(Math.random()*10) + 1); //7

// In case of a range between min and max
const min = 10
const max = 20

console.log(Math.random() * (max - min + 1)) //5.951282802359456

//To get single digit output, min 10 needed
console.log(Math.floor(Math.random() * (max - min + 1)) + min) //19

```


</b>
