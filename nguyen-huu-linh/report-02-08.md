# Report 02/08

## Javascript

- Scope (30%)

  ### Global scope

  - That all variables defined outside the functions will become global, and only one Global scope Variables in the global scope can be accessed and changed from any other scope.

    > Ex:

    ```javascript
    var gl = 2;
    function print() {
      console.log(gl);
    }
    myFunc(); // Output: 2
    ```

  ### Local scope

  - Variable defined inside functions are in local scope. And these variable are different scope than variable in other functions nor can it be accessed from the global scope. That means variables with the same name can be used in different functions without fear of conflicts or overriding.

    > Ex:

    ```javascript
    function lg() {
      var a = 2;
    }
    console.log(a); // Output: Uncaught SyntaxError: Unexpected token
    ```

  ### Function scope

  - All scopes in javascript are created only with functions scope, scopes will not be created in block statements like `<for>`, `<while>` or `<if>` or `<swich>` statements

    > Ex:

    ```javascript
    if true {
        var test = "Inside if statemment";
    };
    console.log(test); // output: Inside if statemment
    ```

  ### Lexical Scope

  - Lexical scope is the accessibility of variables in an inner function to its parent scopes. (but converse is not true parent scope will not access children scope)

    > Ex:

    ```javascript
    function fatherFunction() {
      var fatherName = "Peter";
      function childFunction() {
        console.log(fatherName); //Peter
      }

      childFunction();
    }

    fatherFunction();
    ```

## Issues

- I have some difficulfy reading the documentation and there are some concepts i don't really understand
