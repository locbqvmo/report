# === Enday 04/08 ===

## Javascript

- ES6 (50%)

    ### Definition

    - ES6 stands for ECMAScript 6. ECMAScript was created to standardize JavaScript, and ES6 is the 6th version of ECMAScript, it was published in 2015, and is also known as ECMAScript 2015. There are some major new topics such as:
        * Let & const
        * Template literals
        * Arrow function
        * Classes
        * Default parameter values
        * Enhanced object literals
        * Destructuring
        * Spread
        * Tagged template Jiterals
        * Modules
        * Optional chaining 

    - `var, let` and `const` are used to declare a vairable, but the different between `var, let` and `const` at this update of ES6 are **Scope** and **Hoisting** (`Hoisting` is mentioned at previous report). The variable is declared by using `var` become a global variable and redeclare even when it is placed inside a function or a block code:

    ```Javascript
        {
            var test = 123;
            let test1 = 'Hello';
        }

        console.log(test)   //Expected Output: 123
        console.log(test1)  //Expected Output: test1 is not defined
    ```

    It can be able to cause problems for debug. 

    - Normally, we use plus string for displaying string with Javascript variable:
    
    ```Javascript
        let fullname = 'Vu Hai Nam';
        console.log('My name is ' + fullname);   //Expected Output: My name is Vu Hai Nam
    ```
    But in ES6, we can use `Template literals` which is more flexible:

    ```Javascript
        let fullname = 'Vu Hai Nam'
        console.log(`My name is ${fullname}`); //Expected Output: My name is Vu Hai Nam
    ```

    The output is the same with previous example, but we can see it is pretty convinient and save the time by using a dollars sign and a pairs of curly brace, then we embed Javascript code inside them. In adidtion, before appearing of `multiple code` in ES6, we have to use `\` character to be escape character in order to create a new line:

    ```Javascript
        console.log('line 1\\nline 2\\nline 3\\n');
    ```

    But now we can use `multiple line string` by entering directly at console.log:
    
    ```Javascript
        console.log(`Line 1
        Line 2
        Line 3
        `)
    ```

    - `Arrow function` is the another way for declaring a new function at ES6:

    ```Javascript
        let myFunc = () => {
            console.log('Hello World');
        }
    ```

    - `Classes` is other way for writing constructor function. At ES5 we use `prototype` for show the inheritance property but in ES6 we can use `Class` instead. But in this report I won't mention the inheritance.

    ```Javascript
        //Constructor Function
        function Person(name, age) {
            this.name = name;
            this.age = age;
            this.getAge = function() {
                return this.age;
            }
        }

        let person1 = new Person('Vu Hai Nam', 21);
        
        //Class
        class Animal {
            constructor(name, color) {
                this.name = name;
                this.color = color;
            }

            getName() {
                return this.name;
            }
        }

        let mouse = new Animal ('Jerry', 80);
    ```

    Using `class` instead of using `constructor function` can help for managing the code easily.

    - Based on specific scenario, there are some scenario you want to set the default value, you will use like this:

    ```Javascript
        function logger(log) {
            if(typeof log == 'underfined') {
                log = 'Default value';
            }
            console.log(log);
        }
    ```

    In ES6 you dont need to use `if .. else` statement, you can use `default parameter value`:

    ```Javascript
        function logger(log = 'default') {
            console.log(log);
        }
        
        logger()            //Expected Output: default
    ```

    - `Enhance Object Literals` can help you in defining the variable for key and value of object shortly (Name of key and value is the same)

    ```Javascript
        //Normal way
        var name = 'Vu Hai Nam';
        var age = 21;

        var person = {
            name = name;
            age = age;
        }

        //Use Enhanced object literals
        var person = {
            name,
            age,
        }
    ```

    Defining method for object by removing `: function` keywords, like this:

    ```Javascript
        //Normal way
        var name = 'Vu Hai Nam';
        var age = 21;
        var person = {
            name = name,
            age = age,
            getName = function() {
                return name;
            }
        }

        //Use Enhanced object literals
        var person = {
            name,
            age,
            getName() {
                return name;
            }
        }
    ```
    And defining key for object in variable format:
    
    ```Javascript
        var fieldName = 'name';
        var filedPrice = 'price';

        const course = {
            [fieldName]: 'Javascript',
            [fieldPrice]: 1000,
        }

        console.log(course);   //Expected Output: {name: "Javascript", price: 1000};
    ```

- Async/Await (50%)

    ### Definition

    - Async/Await is a features in Javascript in order deal with asynchronous function:

    ```Javascript
        // cách 1:
        function getJSON() {
            return new Promise(function (resolve) {
            axios.get('https://tutorialzine.com/misc/files/example.json')
                .then(function (json) {
                    resolve(json);
                });
            });
        }
        // cách 2:
        // Async/Await approach
        // The async keyword will automatically create a new Promise and return it.
        async function getJSONAsync() {
            let json = await axios.get('https://tutorialzine.com/misc/files/example.json');
            return json;
        }
    ```
