# === DAILY REPORT 05/08 ===

## Pham Ngoc Chien 05/08

**Today**

- Async & Performmance

  - Ajax request: Ajax stands for Asynchronous Javascript And Xml. Ajax is just a means of loading data from the server and selectively updating parts of a web page without reloading the whole page. Basically, what Ajax does is make use of the browser's built-in XMLHttpRequest (XHR) object to send and receive information to and from a web server asynchronously, in the background, without blocking the page or interfering with the user's experience.

- Es6 Class

- ES6 & Beyond

  - Default parameters: allow named parameters to be initialized with default values if no value or undefined is passed

    ```
        function defaultParameter(a, b=1){
            console.log(a * b )
        }
        defaultParameter(2) //2 since there is no b, the function will take the available b
        defaultParameter(2,3) //6
        defaultParameter(5) //5
    ```

    - Object
      ```
          function defaultParameterObject({name}={name: "Chiến"}){
              console.log(name)
          }
          defaultParameterObject({name:"Chiến2"}) //Chiến2
          defaultParameterObject()//Chiến
      ```
    - Array
      ```
        function defaultParameterObject([name]=["Chiến"], [name2]=["Chiến2"]){
            console.log(name + name2) ;
        }
        defaultParameterObject(["Lương"], ["Lương2"])
      ```

  - Map() method creates a new array populated with the results of calling a provided function on every element in the calling array.

    ```
      var arr = ["Chiến", "Chiến", "Chiến"]
      let arr2 = arr.map((x)=>{
          return x + " Số 1";
      })
      console.log(arr2)
    ```

  - Set() store unique values of any type.
    ```
        const letters = new Set(["a","b","b"]);
        console.log(letters) //{"a","b"}
    ```
    ```
        const numbers = [2,3,4,4,2,3,3,4,4,5,5,6,6,7,5,32,3,4,5]
        console.log([...new Set(numbers)]
    ```

- edit CV (completed)

**None**

- None
