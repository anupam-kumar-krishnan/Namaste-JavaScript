
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
