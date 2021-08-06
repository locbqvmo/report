# === DAILY REPORT 06/08 ===

## Pham Ngoc Chien 06/08

**Today**

- Async & Performmance

  - The yield keyword is used to pause and resume a generator function (function\* or legacy generator function).

    ```
        function *plus(x){ // *: initialization yield
            return y = x + (yield "no variable y")
        }
        var other = plus(1) // pass 1 in function plus
        var it = other.next() // run next step
        console.log(it.value) //result: 1

        it = other.next(2) //result: 3
        console.log(it.value)
    ```

  - Fetch API is a simple API for sending and receiving requests using js. With fetch it's easier to make web requests and handle responses than with the old XMLHttpRequest.

    ```
        function start(){
            getCourses(renderCourse)
        }
        start()
        function getCourses(callback){
            fetch('https://jsonplaceholder.typicode.com/posts') // call API to URL
            .then(function(res){  //receiving data and return Json
                 return res.json()
            })
            .then(callback)  // after .then above done, data will be transmitted renderCourse and render to the screen
            .catch(function(err){
                console.log(err)
            })
        }
        function renderCourse(courses){
            var listCourse = document.querySelector('#list') //take item
            var htmls = courses.map(function(course){  // using map to repeat items
                return `
                <li class="course-item-${course.userId}">
                    <h1>${course.id} </h1>
                    <h1>Title: ${course.title}<h1/>
                    <p>Content: ${course.body}<p/>
                </li>
                `
            })
            listCourse.innerHTML = htmls.join('') // print to the screen
        }

    ```

  - ES6 & Beyond
    -Array.of() method creates a new Array instance from a variable number of arguments, regardless of number or type of the arguments.

    ```
        console.log(Array.of(7,1,2,3,2,1,3))
        //result: [7,1,2,3,2,1,3]
    ```

    - Array.from() method returns an Array object from any object with a length property or any iterable object

    ```
        console.log(Array.from('boo'));
        // result: Array ["b", "o", "o"]

        console.log(Array.from([1, 2, 3], x => x + x));
        // result: Array [2, 4, 6]
    ```

    - find() method returns the value of the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.

    ```
        const array1 = [5, 12, 8, 130, 44];
        const found = array1.find(element => element > 10);
        console.log(found);
        // result: 12
    ```

    - The findIndex() method returns the index of the first element in the array that satisfies the provided testing function. Otherwise, it returns -1, indicating that no element passed the test.

    ```
        const numbers = [4, 9, 16, 25, 29];
        let first = numbers.findIndex(myFunction);
        function myFunction(value, index, array) {
            return value > 18;
        }
    ```

    - Math
      - Math.trunc(x) returns the integer part of x
      - Math.sign(x) returns if x is negative, null or positive
      - Math.cbrt(x) returns the cube root of x
        Math.log2(x) returns the base 2 logarithm of x
      - Math.log10(x) returns the base 10 logarithm of x

**Issues**

- None
