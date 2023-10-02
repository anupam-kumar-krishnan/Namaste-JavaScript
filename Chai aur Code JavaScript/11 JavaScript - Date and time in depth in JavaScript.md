## _Lecture 13 - Date and time in depth in JavaScript_

### _Date📅_
<b>

```js
let myDate = new Date()
console.log(myDate); 
// 2023-10-02T12:22:23.962Z

console.log(myDate.toString()); 
// Mon Oct 02 2023 17:54:00 GMT+0530 (India Standard Time)

console.log(myDate.toISOString());
// 2023-10-02T12:25:48.637Z

console.log(myDate.toLocaleString());
// 2/10/2023, 5:55:48 pm

console.log(myDate.toJSON());
// 2023-10-02T12:25:48.637Z

let myCreatedDate = new Date(2023, 0, 23);
console.log(myCreatedDate.toDateString());
// Mon Jan 23 2023

let myCreatedDate = new Date(2023, 0, 23);
console.log(myCreatedDate.toLocaleString());
// 23/1/2023, 12:00:00 am

let myCreateDate = new Date("2023-01-14");
console.log(myCreateDate.toLocaleString());
// 14/1/2023, 5:30:00 am

let newDate = new Date("01-14-2023");
console.log(newDate.toLocaleString());
// 14/1/2023, 12:00:00 am
```

### _Timestamps ⌛_

```js
let myTimeStamp = Date.now()
console.log(myTimeStamp);
// 1696250540174 (in millisecond)

let newDateGetTime = new Date("01-14-2023");
console.log(newDateGetTime.getTime());
// 1673634600000

console.log(Date.now());
// 1696250815734

console.log(Math.floor(Date.now()/1000));
// 1696250911

let newwDate = new Date()
console.log(newwDate);
// 2023-10-02T12:51:08.464Z

console.log(newwDate.getDay()); // 1
console.log(newwDate.getMonth()++1); // 10
console.log(newwDate.getFullYear()); // 2023
console.log(newwDate.getMonth()); // 9

newwDate.toLocaleString("default", {
  weekday: "long",
});
```



</b>


