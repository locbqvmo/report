# === Enday 02/08 ===

## Javascript

- Scope (30%)

    ### Definition
    - The scope is the range of using or accessing the variable in program. There are three types of scope in Javascript:
        * Global scope: if the variable is declared with global scope that means you can be able to access and us this available anywhere.
        * Block scope: it determines the variable can be accessed in a block of code. It usually get started by curly braces and declared by **let** and **const** keywords.
        * Local scope: it determines the variable can be accessed in a body of a function.
    

    ### Application
    - For global scope:
        ```javascript
            var a = 1;
            function myFunc() {
                console.log(a);
            }
            myFunc();   // Output: 1
        ```
        
        In this example, I have just declared variable a outside the function myFunc(), but I still have the permission to print it out inside the myFunc().
    
    - For block scope:
        ```Javascript
            {
                const age = 18;
                console.log(age);
            }
        ```
        
        In the code snippet above, we can see that age variable can be logged easily, but let's try move this declaration out of block.
        
        ```Javascript
            {
                console.log(age);
            }
            const age = 18;
        ```
        So for this code snippet, the program will throw an exception or error about **'ReferenceError: age is not defined at ....'**. We can replace **const** to **let** then the output won't change.

    - For local scope:
        ```Javascript
            function logger() {
                var fullName = 'Vu Hai Nam';
                console.log(fullName);
            }
            logger();
        ```
        The range of local scope will create when the body of code block is executed. If we stand out of the body of function logger(), If we try to access **fullname** variable, it will throw the same error at previous example. let take another example

        ```Javascript
            function logger() {
                function logger2() {
                    console.log('Logger 2');
                }

                logger2();
            }

            logger2()  //error
            logger()  //Logger 2
        ```
        Because **logger2()** is declared insided **logger()** function, due to we can only able to call **logger2()** when we call **logger()**.

- Closure (20%)

    ### Definition

    - Closure is the combination of bundled function together. It gives you an access to an outer function from inner function. 

    ## Application

    - For instance:
        ```Javascript
            function makeFunc() {
                var name = 'Vu Hai Nam';
                function displayName() {
                    alert(name);
                }
                return displayName;
            }

            var myFunc = makeFunc();
            myFunc();
        ```
        The out of this code snippet is an inform window will popup by alert() function, and the content here is the value of **name** variable.
        
## Issues

- None