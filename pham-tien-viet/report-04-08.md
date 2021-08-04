# 04/08 
## Javascript
**Types and Grammar**

**Types** : available 6 value types (Primitive data types)

> - Null : means nothing. We can understand that something doesn't exist 

>       Ex : 

        typeof null === "object"; // true
        var a = null;
        (!a && typeof a === "object"); // true

> - Undefined : is variables that have no value 

>       Ex : 

        var a;
        typeof a; // "undefined"
        var b = 42;
        var c;
        // later
        b = c;
        typeof b; // "undefined"
        typeof c; // "undefined"

> - Boolean : Boolean has only 2 values, `true` or `false`

>       Ex :

        Boolean(100); //true
        Boolean("hello"); //true
        Boolean(0); //false
        Boolean(""); //false

> - Number : 

>       Ex : 

        var a = 0.42;
        var b = .42;

> - String : is a set of characters

>       Ex : 

        var lastName = 'Viet';
        var firstName = 'Pham'

> - Symbol : is a data type generated to produce unique values, each generated symbol will have a different value and that value is unique. 

>       Ex :

        let symbol1 = Symbol();
        let symbol2 = Symbol('symbol2');
        console.log(symbol1 === symbol2); // false

>        Ex :

        let sym1 = Symbol('hello');
        let sym2 = Symbol('hello');
        sym1 = String(sym1);
        sym2 = String(sym2);
        console.log(sym1 === sym2); // true

> **Value types** : When the variable is initialized, the variable is allocated a memory area and a value  . When the variable is edited, the memory area and the value change to the new memory area and value 

>       Ex :

            let a = 1
            let b = a
            a = 2
            console.log(b) // 1

**Types** : available 3 pefenrece types (Primitive data types)

> - Array : 

>       Ex :

        var a = [1,2,3,4,5]
        var b= [a,b,c,d]

> - Object : is comnination of attributes or methods 

>       +  Attributes : about key and value
>       + Method : is a funtion is initialized in object

>        Ex : 

        function User(firstName, lastName){
            User.firstName = firstName;
            User.lastName = lastName;
            User.getName = function(){
                return `$(User.firstName) $(User.lastName)`
            }
        }
    * User.firstName is attributes
    * User.getname is method

> - Function :

>       Ex :

        function sum(a,b){
            c = a + b
            return c;
        }

**Pefenrece types** : When variable is initialized, a memory area is created to store the initial content of the variable, returns the memory area address to the variable. Then the variable will store the address of the memory area, not the content of the memory area.


> - When declare this variable by other variables, ie are assigned memory area address and memory area values . Call to variable, Js will access to memory area and given content of memory area

>       Ex : 

        const a = {
            name = 'Mercedes'
        }
        const b = a
        a.name = 'BMW'
        console.log(b.name) // 'BMW'



**Grammar** : The basic syntax of the JavaScript language (JS), including how to declare variables, data types, and how to write code. 
> - The syntax of JavaScript is largely borrowed from Java, but JS is also influenced by the syntax of other programming languages such as Awk, Perl, and Python. JavaScript is a programming language that uses the Unicode character standard, and when writing, it is also necessary to pay attention to case-sensitive. 
> - In JavaScript, commands (also called statements), are separated by a semicolon (;). Spaces, tabs, and newline characters are called spaces .

>       Ex : 

        let sym1 = Symbol('hello');
        let sym2 = Symbol('hello');
        sym1 = String(sym1);
        sym2 = String(sym2);
        console.log(sym1 === sym2); // true

> - Comments : 

>       Ex : 

        // a one line comment >       
        /* this is a longer, 
        multi-line comment.
        */      
        /* You can't, however /* nest comments */

> - Variable : variables as symbolic names for values in the program. Variable names, called identifiers, follow certain rules. There are 3 types of declarations in JavaScript. 

>       Ex : 

        Number_hits, temp99, và _name.

> - var : Declare a variable that is accessible throughout the function containing it.

>       Ex : 

        function foo() { 
            var x = 10; 
            if (true) { 
                var x = 20; 
                console.log(x); 
            } 
            console.log(x);
        }

> - let : Declare a variable that is only accessible in the block that surrounds it. 

>       Ex :

        function foo() { 
            let x = 10; 
            if (true) { 
                let x = 20; 
                console.log(x); 
            } 
            console.log(x); 
        }

> - const : Declare a constant – a value that cannot be changed during runtime. 

>       Ex : 

        const A = 5; 
        A = 10; // Uncaught TypeError

**Async and Performance**

**Call Back** : is a function that is passed as an argument when calling another function 

>       Ex : 

        function myFunction(param){
                param('La gia tri')
        }
        function myCallback(value){
                console.log('Value: 'value);
        }
        myFunction(myCallback) 