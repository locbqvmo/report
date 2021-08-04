# Report 04/08

## Javascript

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

- With global scope, when the code is executed in the browser, all global variables and functions are defined on the `window` object.
- if using strict mode then this = undefined
- Arrow function doesn't have "this". It will refer to its outer this object

  ```javascript
  var users = {
    name: "Linh",
    age: 21,

    showInfo() {
      let arrow = () => {
        console.log(this.name);
      };
      arrow();
    },
  };

  users.showInfo(); //output: Linh
  ```

- change this reference to another object

  ```javascript
  var user = {
    name: "LINH",
    age: 21,
  };

  var showInfo = {
    name: "lii",
    age: 12,
    show: function () {
      console.log("I'm " + this.name + " and I " + this.age);
    },
  };
  const run = showInfo.show.bind(user);
  run();
  ```

**_Object prototypes_**

- Prototype is the mechanism by which objects in javascript inherit features from another object. All objects in javascript have a prototype, and these objects inherit properties and methods from their prototype.

## Issues

None
