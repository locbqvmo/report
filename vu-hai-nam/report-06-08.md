# === Enday 04/08 ===

## Javascript

- ES6 (80%)

    ### Definition

    - ES6 provided a helpful feature allow developers to seperate data stored inside Object and Array and assign them to another seperate varaible (It is called `Destructuring`). In `Destructuring` we also have `Rest parameter` for using to seperate data.

    ### Application

    - For object:

    ```Javascript
        let obj1 = {
            name: 'Vu Hai Nam',
            age: 21,
        }

        let { name, age } = obj1;
        console.log(name);          //Expected Output: 'Vu Hai Nam'
        console.log(age);           //Expected Output: 21
    ```

    In this example, I have used destructuring in order to seperate two attribute and assign them to two new variable which have the same name with the attributes of `obj1` object. In addition, we can use `rest parameter` to do the same thing.

    ```Javascript
        let obj1 = {
            name: 'Vu Hai Nam',
            age: 21,
            address: 'Ha Noi',
        }

        let { name, ...rest} = obj1;
        console.log(name);         //Expected Output: Vu Hai Nam
        console.log(rest);         //Expected Output: { age: 21, address: 'Ha Noi' }
    ``` 

    In this example, `...rest` is representing for the rest or the remaining elements of the object and stores them in a object. In array, we can do the similar syntax.

    ```Javascript
        let arr1 = [1 , 2, 3, 4 , 5];
        let [ first, ...rest ] = arr1;
        console.log(first);         //Expected Output: 1
        console.log(rest);          //Expected Output: [ 2, 3, 4, 5 ];
    ```

    In this instance, we can see the difference here is instead of using curly braces, using parentheses in order to store and seperate array.

    ### Definition

    - `Spread Operator` can be used when all elements from an object or array need to be included in a list of some kind.

    ### Application

    - For example:

    ```Javascript
        let num1 = [1 , 2, 3];
        let num2 = [...numbers];
        console.log(num2)           //Expected Output: [1, 2, 3]
    ```

    `Rest parameter` syntax looks exactly like `spread` syntax. In a way, `rest` syntax is the opposite of `spread` syntax. `Spread` syntax **expands** an array into its elements, while `rest` syntax collects multiple elements and "condenses" them into a single element.

- Modules (50%)

    ### Definition

    - `Moudules` are reuseable pieces of code in a file that can be ***exported*** and then ***imported*** for using in another file. A modular program is one whose components can be seperated, used individually, and recombined to create a complex system. 

    - There are multiple ways of implementing modules depending on the runtime environment in which your code is executed. In Javascript, there are two runtime environments and each has a prefered module implementation:      
        * The `Node` runtime environment and the `module.exports` and `require()` syntax.
        * The browser's runtime environment and the `ES6` `import`/`export` syntax;

    ### Applicaiton 
    
    - For example, we have created two seperated files, first one is `area-library.js` which includes two function in order to calculate the area of circle and square, the last one is `app.js` which is the place will run the program. And the following example, I will focus on using the `module.exports()` and `require()` syntax in the `Node` runtime environment.

    ```Javascript
        /* In area-library.js */
        const PI = Math.PI;

        const circleArea = r => {
            return PI * r * r;
        }

        const squareArea = side => {
            return side * side;
        }

        module.exports.circleArea = circleArea;
        module.exports.squareArea = squareArea;
    ```

    We `exports` two functions in order to use in another file, and `require()` to use them.

    ```Javascript
        /* app.js */
        const radius = 5;
        const sideLength = 10;

        const areaFunctions = require('./area-library.js');
        const areaOfCirle = areaFunctions.circleArea(radius);
        const areaOfSquare = areaFunctions.squareArea(sideLength);
    ```