# === DAILY REPORT 03/08 ===

## Pham Ngoc Chien 03/08

**Today**

- Scope & closures (60%)

  - Scope:

    - types of scope:

      - Global
      - Code block (let, const)
      - local scope (var, function)

    - How a variable is accessed: get the closest variable declared before it

    - Functions can access variables declared in its scope and outside it

    - Global variables can be accessed from anywhere in a JavaScript program.

    ```
        var globalScope1 = "message1";
        function global2(){
            console.log("function global 2")
        }
        function global(){
            console.log(globalScope1);
            global2()
        }
        global()
    ```

    - const, let are not usable outside block scope but var can

    ```
    {
        let blockScope2 = "blockScope2";
        var a = 18;
        console.log(blockScope2)
    }
    {
        var a = 1;
    }
    console.log(a)
    ```

    - when calling each function there is always a new scope created

    ```
    function nummber (one, two, three){
        console.log(one, two, three);
    }
    nummber (1, 2, 3);
    nummber (4, 5, 6);

    ```

  - Closures:

    - A function can remember where it was created and can access variables outside of its scope

    ```
        function Counter(){
            let counter = 0;
            function increase(){
                return ++counter
            }
            return increase;
        }
        const couter1 = Counter()
        console.log(couter1()) //(result: 1)
        console.log(couter1()) //(result: 2)
        console.log(couter1()) //(result: 3)
    ```

- Object Prototypes (70%)

  - All JavaScript objects inherit properties and methods from a prototype.

  ```
      function Person(firstName, lastName, age) {
      this.firstName = firstName;
      this.lastName = lastName;
      this.age = age;
      }
      Person.prototype.national = "VietNam"
      const myFather = new Person("John", "Doe", 50);
      const myMother = new Person("Sally", "Rally", 48);

  ```

  ```
    function person (name, age){
    this.name = name;
    this.age = age;
    }
    person.prototype.info = function(){
        console.log("infor: " + this.name + " " + this.age)
    }
    function person1 (nationality){
        this.nationality = nationality;
    }
    person1.prototype = new person();
    person1.prototype.showNationality = function(){
        console.log("Quốc tịch: " + this.nationality)
    }

    var Nam = new person1("Việt nam");
    Nam.name = "Nam";
    Nam.age = "21";

    var Chien = new person1("Việt nam");
    Chien.name = "Chien";
    Chien.age = "21";

    Nam.info();
    Nam.showNationality()

    Chien.info();
    Chien.showNationality()
  ```

- Types & Grammar (70%)

  - JavaScript defines seven built-in types:

    - null
    - undefined
    - boolean
    - number
    - string
    - object
    - symbol -- in ES6!

    ```
        var a = null;
        (!a && typeof a === "object"); // true
        typeof undefined     === "undefined"; // true
        typeof true          === "boolean";   // true
        typeof 42            === "number";    // true
        typeof "42"          === "string";    // true
        typeof { life: 42 }  === "object";    // true
        // added in ES6!
        typeof Symbol()      === "symbol";    // true
    ```

  - The Function Data Type: The function is callable object that executes a block of code. Since functions are objects, so it is possible to assign them to variables. Functions can be used at any place any other value can be used. Functions can be stored in variables, objects, and arrays.

    ```
        var greeting = function(){
            return "Hello World!";
        }

        // Check the type of greeting variable
        alert(typeof greeting) // Output: function
        alert(greeting());     // Output: Hello World!
    ```

  - The typeof Operator: The typeof operator can be used to find out what type of data a variable or operand contains

**Issues**

- Don't understand much about closures
