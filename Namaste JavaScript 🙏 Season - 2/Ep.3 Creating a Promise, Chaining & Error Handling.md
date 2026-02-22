# _Creating a Promise, Chaining & Error Handling_

## Creating a Promise in JavaScript
> A Promise represents a value that may be available now, later, or never.

<b>
  
```js
const myPromise = new Promise((resolve, reject) => {
    let success = true;

    if (success) {
        resolve("Operation successful!");
    } else {
        reject("Operation failed!");
    }
});
```
 
</b>

`resolve(value)` → called when operation succeeds

`reject(error)` → called when operation fails
