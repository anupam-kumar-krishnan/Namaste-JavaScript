## _Scope_



### _Can we access b inside function a()_
- JavaScript will try to find out weather b exists in the local memory space or not 
- JavaScript will try to find out this b inside a's Execution Context, but it will not be found as we never created b inside that function
- Now what will happen/ Will it print `undefined`- that special placeholder or `not defined`?
- This print 10 as an output, that means somehow inside the function, this `b` can _**access**_ the `b` which is _**outside the function**_ 

<b>

```js
function a() {
 console.log(b);
}
var b = 10;
a();

// Output
// 10
```
### _Can I access b now?_
- Yes, still I can access `b

```js
function a() {
  c();
  function c(){
    console.log(b);
  }
}

var b = 10;
a();

// Output
// 10
```

</b>

### _Can I access b outside the function_

<b>

```js
function a(){
   var b=10;
   c();
   function c(){
 
   }
}

a();
console.log(b);

//Output
//b is not defined
```
</b>

## _Scope_
- Scope means where you can access a specific variable or a function in our code
- Scope is directly dependent on the `Lexical Environment`

_**There are 2 ways to look at this:**_
- Where can I access this variable b(here in example)
- Is b inside the scope of function c(Can I access b inside c)

