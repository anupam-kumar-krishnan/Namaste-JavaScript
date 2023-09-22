## _Datatypes Summary in Javascript_

### _Datatypes in JavaScript are divided into two parts:_
- _**Primitive Datatype** (Call by Value)_
- _**Non-Primitive Datatype** (Call by Reference)_

## _Difference b/w Primitive and Non-Primitive Datatype_
### **_Primitive Datatype:_**
- String
- Number
- Boolean
- Null
- Undefined
- Symbol
- BigInt

### **_Non-Primitive Datatype:_**
- Array
- Objects
- Functions

## _Is JavaScript Dynamically typed language or Statically typed?_
- **_Dynamically Typed Language_** <br>
JavaScript is a dynamically typed language, which means that data types of variables
are determined by the value they hold at runtime and can change throughout the program
as we assign different values to them.

## _How to define Symbol_
<b>

```js
const id = Symbol("123");
const anotherId = Symbol("123");
console.log(id === anotherId); // false
```
</b>

**_Even if both are looking same, but the return value will not be same_**

### _Array_
<b>

```js
const heros = ["shaktiman", "naagraj", "doga"]
```

### _Object_

```js
let myObj = {
    name: "Hitesh",
    age: 42,
}
```

### _Function_

```js
const myFunction = function(){
    console.log("Hello World");
}

console.log(typeof myFunction); //function
```

### _Big Integer_
```js
let bigNumber = 123456978n;
console.log(typeof bigNumber); //bigint
```
</b>

## _Return type of variables in JavaScript_
### _Primitive Datatypes_
- Number => Number
- String => String
- Boolean => Boolean
- null => object
- undefined => undefined
- Symbol => Symbol
- BigInt => bigInt

### _Non Primitive Datatypes_
- Arrays => Objects
- Function => Function
- Object => Object























