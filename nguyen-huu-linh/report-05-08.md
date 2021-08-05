# Report 05/08

## Javascript

**_Object prototypes_**

- Prototype is the mechanism by which objects in javascript inherit features from another object. All objects in javascript have a prototype, and these objects inherit properties and methods from their prototype.

- In JavaScript, all objects have a prototype. And those objects will inherit properties and methods from its prototype.

- JavaScript is a prototype-based language, so whenever we create a function using JavaScript, JavaScript engine adds a prototype property inside a function.

- When creating an object with the new keyword, new objects inherit all properties from [[Prototype]]

**_Types and Grammar_**

**Types** : available 6 value types (Primitive data types)

> Null : means nothing. Null is a Object

```javascript
typeof null === "object"; // true
var a = null;
!a && typeof a === "object"; // true
```

> Undefined : is variables that have no value

```javascript
var a;
typeof a; // "undefined"
a = 21;
consolole.log(a); //21
```

> Boolean : Boolean has only 2 values, `true` or `false`

```javascript
var a = 12;
var b = 21;

if (b - a === 9) {
  console.log(true);
} else {
  console.log(false);
}

// true
```

> Number : Number is a primitive wrapper object used to represent and manipulate numbers like 37 or -9.25.

```javascript
var a = 21;
var b = 3.14;

console.log(typeof a); // number
```

> String : is a set of characters

```javascript
    var name = "Linh";
    console.log(tepeof name) // string
```

> Symbol :It was first introduced at ECMAScript 2015 (ES6) and it is a data type generated to produce unique values, each generated symbol will have a different value and that value is unique.

```javascript
let symbol1 = Symbol();
let symbol2 = Symbol("some text");
console.log(symbol1 === symbol2); // false
```

**_type reference_**: Array, Object, Function

- Array : The JavaScript Array class is a global object that is used in the construction of arrays; which are high-level, list-like objects.

```javascript
var a = [1, 2, 3, 4, 5];
var users = [
  { name: "LINH", age: 21 },
  { name: "A", age: 20 },
];
```

> Object : is comnination of attributes or methods

- Attributes : about key and value
- Method : is a funtion is initialized in object

```javascript
var info = {
  name: "linh",
  age: "21",
  showInfo: function () {
    console.log(`My name ${this.name} and I ${this.age}`);
  },
};

info.showInfo();
```

> Function : A JavaScript function is a block of code designed to perform a particular task.
> A JavaScript function is executed when "something" invokes it (calls it).

```javascript
function car(name) {
  console.log(name);
}

car("vinfast");
```

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

## Issues

None
