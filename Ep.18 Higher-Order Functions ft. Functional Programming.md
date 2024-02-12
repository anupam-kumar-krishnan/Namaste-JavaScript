# _Higher-Order Functions ft. Functional Programming_

## _Introduction to Functional Programming_
- Functional Programming is not possible without the _**Higher Order Functions**_

## _What is Higher Order Functions?_
- _**Definition of Higher Order Function:**_ 
  - A function which takes another function as an Argument or returns a function from it is known as _**Higher Order Function.**_

<b>

```js
function x(){
  console.log("Namaste");
}

function y(x){
   x();
}
```
</b>

- **_Let's take an example:_**

<b>

```js
const radius = [3, 1, 2, 4];

const calculateArea = function (radius){
    const output = [];
    for(let i=0; i < radius.length; i++){
      output.push(Math.PI * radius[i] * radius[i]);
    }
  return output;
};

const calculateCircumference = function (radius){
    const output = [];
    for(let i=0; i < radius.length; i++){
      output1.push(2*Math.PI * radius[i]);
    }
  return output;
};

const calculateDiameter = function (radius){
    const output = [];
    for(let i=0; i < radius.length; i++){
      output.push(2 * radius[i]);
    }
  return output2;
};

console.log(calculateArea(radius));
console.log(calculateCircumference(radius));
console.log(calculateDiameter(radius));

// Output
// [28.274333882308138, 3.141592653589793, 12.566370614359172, 50.26548245743669]
```
</b>

- This is not a good way. 

### _Problems in the above code_
- We are Repeatiting Yourself alot (DRY Principle: Don't Repeat Yourself)
  - 90% of the code is same. Only the logic is changing.
  - **_Can we write it in a better way?_**
    - We can abstract the **_logic_** out
    - We will try to make the function **_`Generic`_**
    - We will try to put this logic inside the function from outside i.e. passing logic inide the function

<b>

```js
const radius = [3, 1, 2, 4];

const area = function (radius) {
  return Math.PI * radius * radius;
};

const circumference = function (radius) {
  return 2 * Math.PI * radius;
};

const diameter = function (radius) {
  return 2 * radius;
};

const calculate = function (radius, logic) {
  const output = [];
  for (let i = 0; i < radius.length; i++) {
    output.push(logic(radius[i]));
  }
  return output;
};

console.log(calculate(radius, area));
console.log(calculate(radius, circumference));
console.log(calculate(radius, diameter));

// Output
// [28.274333882308138, 3.141592653589793, 12.566370614359172, 50.26548245743669]
// [18.84955592153876, 6.283185307179586, 12.566370614359172, 25.132741228718345]
// [6, 2, 4, 8]
```
</b>

## _Functional Programming deals with:_
- **_Pure Functions_**
- **_Composition of Functions_**
- **_Reusability_**
- **_Modularity_**

### _Map_
- So the function _**calculate**_ in the above code is exactly similar to the function **_`map`_**
- In the below code we can see, the result of map and calculate is exactly same
- So we can say that we have written our own implementation of map function named as `calculate` here
- **_Map function_** also just creates a new array and then iterate over each of these element in the radius and then returns the output

<b>

```js
const radius = [3, 1, 2, 4];

const area = function (radius) {
  return Math.PI * radius * radius;
};

const circumference = function (radius) {
  return 2 * Math.PI * radius;
};

const diameter = function (radius) {
  return 2 * radius;
};

const calculate = function (radius, logic) {
  const output = [];
  for (let i = 0; i < radius.length; i++) {
    output.push(logic(radius[i]));
  }
  return output;
};

console.log(radius.map(area));
console.log(radius.calculate(area));

// Output
// [28.274333882308138, 3.141592653589793, 12.566370614359172, 50.26548245743669]
// [28.274333882308138, 3.141592653589793, 12.566370614359172, 50.26548245743669]
```
</b>












