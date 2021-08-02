# === DAILY REPORT 30/07 ===

## Pham Ngoc Chien 30/07

**Today**

- Scope & closures (20%)

  - What's the scope?
  - Compiled vs. Interpreted
  - The compiler will have to convert the programming language into machine code and then store the result on the hard drive so it can be executed at the next run.
    - Compiling Code:
      - Before executing code lines, is by the JS engine first parsing the entire program before any of it is executed
      - Functions to have duplicate parameter names, JS engine know . there is a syntaxerror
  - Interpreted: interpreted when the program is written at runtime will be directly into machine code (language that the computer can understand) for the computer to execute them. When the program runs to any command line, it will convert it to machine code that can be executed by the computer
  - Let, const, var: determine the scope of the variable

- this & Object Prototypes (30%)

  - this: this is the face to a object. The object is the owner of the context or is the like the code is being running.

  ```this basic
    var person = {
    name: "ChienPN",
    height: "1m",
    weight: "1000kg",
    information(){
        console.log("information: " + this.name + " " +  this.height +" "+ this.weight)
    },
    action:{
        name: "Pizza",
        eat(){
            console.log("you eat more, eat less!!")
        },
        exercise(){
            console.log(this)
            console.log("do exercise")
        }

      }
    }
    person.information()
    person.action.eat()
    person.action.exercise()
  ```

  ```this basic
    function person(name, age, placeOfBirth){
    this.name = name
    this.age = age
    this.placeOfBirth = placeOfBirth
    this.info = function(){
        console.log('information:', this)
      }
    }
    const boss = new person('ChienPN', '21', 'Nam Định');
    console.log(boss.info()) ;
  ```

  ```this basic
  function person(name, age, placeOfBirth){
    this.name = name
    this.age = age
    this.placeOfBirth = placeOfBirth
    this.info = function(){
        console.log('information:', this)
    }
  }
  person.prototype.eat = function(){
    console.log("eat slowly", this)
  }
  const boss = new person('ChienPN', '21', 'Nam Định');
  console.log(boss) // boss: this
  ```

  ```this basic
  - 'use trick': all lines of code below the use strict declaration line will be managed more strictly in terms of syntax
  function myFunction(){
    console.log(this) // this: window
  }
  myFunction()

  ```

**Issues**

- I don't understand much about "this", I will improve more
