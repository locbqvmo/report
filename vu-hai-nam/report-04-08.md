# === Enday 04/08 ===

## Javascript

- Object Prototype (30%)

    ### Definition

    - Prototypes are the mechanism by which Javascript objects inherit methods and properties from one another. It is important thing in executing OOP model in Javascript. In addition, using prototype is the way to save memory and advoid memory leaking during process of running program.

    ### Applycation

    - The following example will show the inheritance with prototype:

    ```Javascript
        function Person(name, age, address) {
            this.name = name;
            this.age = age;
            this.address = address;
            this.sleep = function() {
                console.log('Sleeping');
            }
        }

        //Create an instance of Human
        let person1 = new Human('Vu Hai Nam', 21, 'Ha Noi');
        console.log(person1);       //Expected Output: Person {name: "Vu Hai Nam", age: 21, address: "Ha Noi"}
        person1.sleep();            //Expected Output: 'Sleeping'
    ```
    In the example above I have declared a constructor function and created a new instance named person1. The instance has all of the properties and method from constructor function. Suddenly, I want to create a new instance named person2 and want to add new action for all person:

    ```Javascript
        function Person(name, age, address) {
            this.name = name;
            this.age = age;
            this.address = address;
            this.sleep = function() {
                console.log('Sleeping');
            }
            this.speak = function() {
                console.log('Speaking');
            }
        }

        let person1 = new Human('Vu Hai Nam', 21, 'Ha Noi');
        let person2 = new Human('Nguyen Van A', 22, 'Ha Noi');

        person1.sleep();            
        person2.speak();            //Expected Output: 'Speaking'
    ```
    After creating person2, we can see person2 have the same ability with person1, but everytime we create a new instance, the program will define two new methods for each instance that is reason can be able to cause leak memory or waste of memory. So we can use prototype like this:

    ```Javascript
        function Person(name, age, address) {
            this.name = name;
            this.age = age;
            this.address = address;
        }

        Person.prototype.speak = function() {
            console.log('Speaking');
        }

        Person.prototype.sleep = function() {
            console.log('Sleeping');
        }

        let person1 = new Human('Vu Hai Nam', 21, 'Ha Noi');
        let person2 = new Human('Nguyen Van A', 22, 'Ha Noi');
        person1.sleep();            
        person2.speak();            //Expected Output: 'Speaking'        
    ```

    The output is the same but the perfomance was improved a lot. However, we dont see the defination of constructor `Person` but two instance still access two methods. Javascript engines was trying to find out these methods on object, if the method do not exist at object, it will continue find out at **prototype object** at **Constructor**, still is not, keep finding at **Object**. Eventually, still cannot find out it will return `undefined`. 

- This (50%)

    ### Definition
    - Using `this` keyword in order to represent for an object which is owner of context. In other words, the `this` keyword refers to the object it belongs to.

    ### Applycation
    - For example:

    ```Javascript
        $('btn').on('click', function() {
            $(this).hide();
        })
    ```
    I have use Jquery for this example. the element `button` has been define a click event. So `$(this)` here is representing for the `button` element which is calling `hide()` function. With `this` keyword, we do need to duplicated the code.

    - For the global scope, `this` will represent for the `window` object:

    ```Javascript
        function doThing() {
            console.log(this);
        }

        doThing();          //Expected Output: Window {0: Window, window: Window, …}
    ```
    - But if we running previously example in `strict mode`, then `this` keyword will return underfine.

- Synchronous and Asynchronous (50%)

    ### Definition

    - In synchronous is everything will be executed or run in order and for asynchronous is the opposite. 
    - For synchronous, imagine that we have a process of retreiving user's data from database, have some set of code for the future show user profile like:
        * step 1: Connect to DB
        * step 2: Retreiving data
        * step 3: Retreiving images
        * step 4: Server sends back data

    However, for some reason like the network or the huge number of data that effect to loading time. Step 2 take one hours, then all the remaining step have to wait for the end of previous step, that will badly effect to UX and many other factors.

    In order to solve the synchronous, we use asynchronous. It is the process in which commands do not need to wait for ending of previous one. In javascript, we have the 3 most commonly used asynchronous handling methods: callback, promise, async/await.

    ### Application
    
    - For callback which is a function passed as a parameter for another function. It ofen use with `setTimeout()` amd `setInterval` function.

    ```Javascript
        function asyncFunc(callback) {
            console.log('Start');
            setTimeout(function() {
                callback();
            }, 2000);
            console.log('Waiting');
        }

        let printEnd = function() {
            console.log('End');
        }

        asyncFunc(printEnd);
        //Expected Output:
        // Start
        // Waiting
        // End
    ```

    In the example, `callback()` function is `printEnd()` and it is passed into `asyncFunc()` as a argument. After waiting 1 second, `sasyncFunc()` call `prinEnd()` in order to run following commands then. But when using callback, there are some disadvantage points like when doing many asynchronous commands so you need to nest callback to each other that makes the code is hard to read, debug or maintain (It's called Callback Hell). So in order to fix that, ES6 provide `Promise` to fix it.

    - A promise is in one of three different states:

        * **pending**: The initial state of a promise. 
        * **fulfilled**: The state of a promise representing a successful operation. 
        * **rejected**: The state of a promise representing a failed operation.

    - For `Promise`, it represents a value that does not yet exist and that will be returned at some future time. `Promise` has an `executor` which get two callbacks like `resolve` and `reject`:

    ```Javascript
        let promise = new Promise(function(resolve, reject) {
            //Asynchronous code
        });
    ```
    - `Promise` will receive a callback function with 2 parameters as follows:
        * **resolve**: a function used to handle after Promise executed successfully
        * **reject**: a function used to handle if the code is asynchronous in the Promise, an error occurs.
    
    - `Promise` also provide three methods used to handle:
        * **then()**: Used to handle after the Promise has been successfully executed (when resolve is called).
        * **catch()**: Used to handle after Promise has any error (when reject is called).
        * **finally()**: Used to handle after Promise has both error and success.

    ```Javascript
        const myPromise = new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve('foo');
            }, 300);
        });

        myPromise
            .then(handleResolvedA, handleRejectedA)
            .then(handleResolvedB, handleRejectedB)
            .then(handleResolvedC, handleRejectedC);
    ```

- Async/await (0)

## Issues
    
- The definition, also the application of using Object Prototype are really confuse. I dont really understand clearly what is **__proto__** at instance or what is exactly **Prototy Object** and **Prototy property**.