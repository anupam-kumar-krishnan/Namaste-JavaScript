# _JavaScript - String_

- _**String**_ is denoted by **`Single Quote`** as well as **`Double Quote`**
<b>

```js
const name = "Hitesh"
const repoCount = 50

console.log(name + " " + repoCount + " repositories"); //Hitesh 50 repositories
// The above syntax is not recomended; it is outdated now

// Modern Way: Interpolation

console.log(`Hello my name is ${name} and my repo count is ${repoCount}`);
//Hello my name is Hitesh and my repo count is 50
```
## _Declare a String_

```js
const gameName = new String('hiteshhhc')
console.log(gameName[0]); //h
console.log(gameName._proto_);  //{} | actually this is not empty

console.log(gameName.length); //9
console.log(gameName.toUpperCase()); //HITESHHHC
console.log(gameName.charAt(2)); //t
console.log(gameName.indexOf('t')); //2
```

![string](https://github.com/anupam-kumar-krishnan/JavaScript-Notes/assets/69143883/21b60818-ef8e-4795-b524-3a3efe912de2)

```js
const gameName = new String('hitesh-hc')


//substring
const newString = gameName.substring(0,4) //ast value positon doesn't get count
console.log(newString); //hite

//slice
const anotherString = gameName.slice(-8,4);
console.log(anotherString); //ite *|Doubt - check|*
// In sclice, we can use negative values
// While, substring doesn't obey negative values i.e. starts only from positive

//trim
const newStringOne = "    hitesh    "
console.log(newStringOne); //    hitesh    
console.log(newStringOne.trim()) //hitesh

//replace
const url = "https://hitesh.com/hitesh%20choudhary"

console.log(url.replace('%20', '-'));
//https://hitesh.com/hitesh-choudhary

//includes
console.log(url.includes('hitesh')); //true

//split
const gameNewName = new String('hitesh-hc-com')
console.log(gameNewName.split('-')); //['hitesh', 'hc', 'com']

```


</b>





