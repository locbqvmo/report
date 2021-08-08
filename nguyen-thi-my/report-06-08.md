## Nguyen Thi My

**map()**: iterates the elements in the array, returns the number of elements equal to the number of elements in the original array

```
let array=[1,2,3,4,5,6]
array.map((item)=>item)
//[1, 2, 3, 4, 5, 6]
```
**sort()** : sort array elements in ascending order
 
 ```
 let array=[2,300,4,50,6]
 array.sort((a,b)=>a-b)
//[2,4,6,,50,300,]
```
**filter()** :filter the elements in the array and return the elements that match the function's condition
```
let array=[2,300,4,50,6];
const copy=array.filter((item)=>item>5);
console.log(copy);
//[300, 50, 6]
```
**concat()**:array concatenation

```
let arr1=[1,2,3];
let arr2=[1,6,78,9];
let copy = arr1.concat(arr2);
console.log(copy);
//[1, 2, 3, 1, 6, 78, 9]
```
**.push()** :adds one or more elements to the end of an array and returns the new length of the array.

```
const animals = ['pigs', 'goats', 'sheep'];

const count = animals.push('cows');
console.log(count);
// expected output: 4
```

**slice()** : method returns a shallow copy of a portion of an array into a new array object selected from start to end (end not included) where start and end represent the index of items in that array. The original array will not be modified.

```
const animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];
console.log(animals.slice())
// ["ant", "bison", "camel", "duck", "elephant"]
console.log(animals.slice(2,4))
//["camel", "duck"]
```
**Common functions when working with Object**
**Object.assign()**:copy 1 or more objects to an object

```
const target = { a: 1, b: 3 };
const source = { d: 4, c: 5 };

const returnedTarget = Object.assign( source,target);

console.log(source);
// expected output: Object { a: 1, b: 4, c: 5 }

console.log(returnedTarget);
// expected output: Object { a: 1, b: 4, c: 5 }

```

**Object.keys()** : Returns an array containing the keys of that object

```
const object1 = {
  a: 'somestring',
  b: 42,
  c: false
};

console.log(Object.keys(object1));
// expected output: Array ["a", "b", "c"]
```
**Object.keys()**:Returns an array containing the values ​​of the object
```
const object1 = {
  a: 'somestring',
  b: 42,
  c: false
};

console.log(Object.values(object1));
// expected output: Array ["somestring", 42, false]

```
**Object.entries()**: method returns an array of a given object's own enumerable string-keyed property [key, value] pairs
```
const object1 = {
  a: 'somestring',
  b: 42
};

for (const [key, value] of Object.entries(object1)) {
  console.log(`${key}: ${value}`);
}

// expected output:
// "a: somestring"
// "b: 42"
```
 

