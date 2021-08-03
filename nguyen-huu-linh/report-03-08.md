# Report 03/08

## Javascript

**CLOSURES**

> Whenever create a function within another function, a closures is also created. The inner function is closure. This closure is usually returned so you can use the outer function's variables at a later time.

```javascript
function myName() {
  const name = "linh";

  function innerName() {
    console.log(name);
  }

  return innerName;
}

myName()();
```

> Private variables with closures

```javascript
function info(name, age) {
  let _name = name;
  let _age = age;

  return {
    infoUsers() {
      console.log(`Hello, My name ${_name} and I ${_age}`);
    },
  };
}

const user = info("linh", 21);
user.infoUsers();
```

**This & Object prototypes**

**_This_**

- This in javaScript is used to represent an Object, the Object that is the subject of the context, or the running object code.
- This is actually a binding that is made when a function is invoked, and what it references is determined entirely by the call-site where the function is called.

  > Ex:

  ```javascript
  var person = {
    name: "Linh",
    age: 21m

    showInfo: function(){
      console.log(this.name + " " + this.age);
    }
  }

  person.showInfo();
  ```

**_Object prototypes_**

> In javascript, all object have a prototype. And those objects will inherit properties and methods from its prototype.

Ex:

- An object created with new Date() will inherit from `Date.prototype`.
- An array created with new Array() inherit from `Array.prototype`.
- An object info will inherit from `info.prototype`.

**Types & Grammar**

> JavaScript defines seven built-in types:
>
> - null
> - undefined
> - boolean
> - number
> - string
> - object
> - symbol -- in ES6!

## Issues

None
