# === DAILY REPORT 04/08 ===

## Pham Ngoc Chien 04/08

**Today**

- Async & performance (60%)

  - Callback

    - In JavaScript, a callback is a function passed into another function as an argument to be executed later.

    ```
        function myFunction(param){
            if (typeof param === 'function'){
                param('Chien')
            }
        }
        function myCallback(value){
            console.log('value: ',value);
        }
        myFunction(myCallback);
        //result: "value: Chien"
    ```

  - Promise

    - Handling asynchronous operations, before having promises we often use callbacks, but callbacks often lead to callback hell (makes the code very confusing and hard to read), with promises (easier to understand) we will overcome this situation
    - To create a promise we will create a promise with the keyword "new" and pass it to an executor function, which will receive two arguments, resolve and reject. Resolve we will call it when the operation succeeds, and reject is when it fails. we will use .then .catch and finally, .then will callback functine it will be executed when prosime resolve(), .catch when receiving reject. .finally() will be run regardless of success or failure.

    ```
        var promise = new Promise(
            function(resolve, reject){
                resolve()
            }
        );

        promise
            .then(function(){
                console.log(1)
            })
            .catch(function(){
                console.log(2)
            })
            .finally(function(){
                console.log(3)
            })

        result: 1 (because in fromise we give resolve)
    ```

    ```
        function sleep(ms){ // a function sleep
            return new Promise(function(resolve, reject){   // create promise cos setTimeOut
                setTimeout(resolve, ms)
            })
        }
        sleep(1000)
            .then(function(){
                console.log(1)
                sleep(1000)
                return 1; // this number one will be transferred to the next .then
            })
            .then(function(data){
                console.log(data + 1)   // this function get  1 and plus 1, we will get 2
                return new Promise(function(resolve, reject){
                    reject("Failed!!!") // 1 promise get reject, .then below will not run and .catch will run
                })
            })
            .then(function(){
                console.log(3)
                return sleep(1000)
            })
            .catch(function(err){
                console.log(err) // Failed!!!
            })
            .finally(function(){
                console.log("ran")
            })
    ```

    - An async function is a function declared with the async keyword, and the await keyword is permitted within them. The async and await keywords enable asynchronous, promise-based behavior to be written in a cleaner style, avoiding the need to explicitly configure promise chains.

    ```
        function run(){
            return new Promise(resolve=> {
                setTimeout(() => {
                    console.log("1 second")
                }, 1000)
            })
        }
        async function start(){
            console.log("Begin")
            const result = await run()
            return result;
        }
        start()
    ```

- ES6 & beyond (50%)

  - Spread syntax (...): allows an iterable such as an array expression or string to be expanded in places where zero or more arguments (for function calls) or elements (for array literals) are expected, or an object expression to be expanded in places where zero or more key-value pairs (for object literals) are expected. Spread syntax can be used when all elements from an object or array need to be included in a list of some kind.

  ```
    let arr = [0, 1, 2, 3]
    let arr2 = [...arr, 4, 5, 6, "seven", "8"]
    console.log(arr)
    console.log(arr2)
  ```

  ```
    function sum(x, y, z) {
        return x + y + z;
    }
    const numbers = [1, 2, 3];
    console.log(sum(...numbers)); //6
  ```

  - Rest syntax looks exactly like spread syntax. In a way, rest syntax is the opposite of spread syntax. Spread syntax "expands" an array into its elements, while rest syntax collects multiple elements and "condenses" them into a single element.

    ```
        function myName (a, b, ...firtName){
        console.log(a)
        console.log(b)
        console.log(firtName)
        }
        myName("Nguyễn", "Thị", "Lấp", "Lánh", "Ánh", "Sao", "Mai")
        //Nguyễn
        //Thị
        //(5) ["Lấp", "Lánh", "Ánh", "Sao", "Mai"]
    ```

  - Destructuring: a syntax that allows you to assign properties of an Object or an Array. - Destructuring array

        - Destructuring Objects allows you to create one or more new variables using the properties of an Object.
        ```
            const person = {
                name: "Chiến đẹp trai =))",
                family : 'Phạm',
                date: '23/08/1999',
            }
            //common syntax
            const name = person.name
            const family = person.family
            const date = person.date
            // Destructuring
            let {name1, family2, date3} = person
            console.log(name1)); //Chiến đẹp trai =))
            console.log(family2); //Phạm
            console.log(date3); //23/08/1999
        ```

        - Array destructuring allows you to create a new variable using the value of each index of the Array.
        ```
            const person = ['head', 'body', 'foot', 'hand']
            const [x, y, z, w] = person
            console.log(x + y + z + w) //headbodyfoothand
        ```

**Issues**

- None
