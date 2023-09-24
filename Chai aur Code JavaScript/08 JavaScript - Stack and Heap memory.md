## _Memory in JavaScript_

### _There are two types of Memory_
## **_Stack_** 
<b><i>
```
- Primitive type 
- will get a copy, original value doesn't change)
```
</b></i>

## **_Heap_** 
<b><i>
```
- Non-Primitive type
- will get reference, original value does change
```
</b></i>

<b>


### _Example of Stack_
```js
let myYoutubename = "HiteshChoudharydotcom";

let anothername = myYoutubename
anothername = "chaiaurcode"

console.log(myYoutubename); // HiteshChoudharydotcom
console.log(anothername); // chaiaurcode

// Here, original value doesn't change i.e. myYoutubename remains as it is
// This is an example of Stack
```


### _Example of Heap_

```
let userOne = {
    email: "user@google.com",
    upi: "user@ybl"
}

let userTwo = userOne

userTwo.email = "hitesh@google.com"

console.log(userOne.email) // hitesh@google.com
console.log(userTwo.email) // hitesh@google.com
// same ouput because the reference for both is same
```
![diagram explanation - non primitive - call by reference](https://github.com/anupam-kumar-krishnan/JavaScript-Notes/assets/69143883/17af3ed6-12aa-4101-85be-6ff092323453)


</b>



