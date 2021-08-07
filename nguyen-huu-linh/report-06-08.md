# Report 06/08

## Javascript

**_Async and Performance_**

**Call Back** : is a function that is passed as an argument when calling another function

```javascript
function A(cb) {
  cb();
}

function callback() {
  console.log("Hello Word");
}

A(callback); // Hello word
```

**Call Back Hell**:

```javascript
setTimeout(function () {
  console.log("Bước 1: Chuẩn bị xay cà phê");
  const data = { cafe: ["Robusta", "Arabica"] };
  console.log("Bước 1: Done");
  setTimeout(function () {
    console.log("Bước 2: Lấy sữa + trộn với cà phê");
    const updateData = { newData: data.cafe[0] + " + sữa ông thọ" };
    console.log("Bước 2: Done");
    setTimeout(function () {
      console.log("Bước 3: Lấy sữa + trộn với cà phê + pha cafe phê");
      const finalResult = { result: updateData.newData + "+ pha bằng phin!" };
      console.log("Bước 3: DONE");
      setTimeout(function () {
        console.log(finalResult);
      }, 0);
    }, 2000);
  }, 2000);
}, 2000);
```

**Promise**: Promise is a mechanism in JavaScript that helps you execute asynchronous tasks without falling into callback hell

```javascript
const p1 = new Promise((resolve, reject) => {
  setTimeout(function () {
    resolve("Đây là p1");
  }, 3000);
});

const p2 = new Promise((resolve, reject) => {
  setTimeout(function () {
    resolve("Đây là p2");
  }, 2000);
});

const p3 = new Promise((resolve, reject) => {
  setTimeout(function () {
    resolve("Đây là p3");
  }, 1000);
});

p1.then(function (data) {
  console.log(data);
  return p2;
})
  .then(function (data) {
    console.log(data);
    return p3;
  })
  .then(function (data) {
    console.log(data);
  });
```

**async await**: is a JavaScript feature that helps us work with asynchronous functions in a way that is more fun and easier to understand. It is built on Promises and is compatible with all API-based Promises.

```javascript
const p1 = new Promise((resolve, reject) => {
  setTimeout(function () {
    resolve("Đây là p1");
  }, 3000);
});

const p2 = new Promise((resolve, reject) => {
  setTimeout(function () {
    resolve("Đây là p2");
  }, 2000);
});

const p3 = new Promise((resolve, reject) => {
  setTimeout(function () {
    resolve("Đây là p3");
  }, 1000);
});

async function get() {
  const a = await p1;
  console.log(a);
  const b = await p2;
  console.log(b);
  const c = await p3;
  console.log(c);
}

get();
```

## Issues

None
