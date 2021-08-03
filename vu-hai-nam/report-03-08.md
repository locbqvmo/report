# === Enday 03/08 ===

## 

- Scope (80%)

    + As I have mentioned last report, there are three types of scope in a javascript program such as  global scope, block scope and local scope. But I did not metion that when is a local scope really remove from memory or a life cycle of a variable ?
        * For global variable, this variable will be released when the program ends or exist. Like web application, when the we press F5 button to refresh the page or we close the tab of web app, then the program will get rid of these global variables of its self.
        * For block and local variable, this will be released when the variable is out of block code, or the function executed completely.
        * For a variable is referenced by a function I will mention at clouser part below.

- Clouser (70%)

    ### Definition

    - Is a function has ability to remember where it was created and access to its outer variable. The purpose of using clouser is in order to code shorter and can apply the private property in OOP (Object-Oriented Programming). Lets consider few example to get digged of it.


    ### Applycation

    - Nowadays, Local-Storage is a perfect place to store some information or some configration of user like theme color (dark color, light color), user's personal information (full name, age, address), etc. So in order to store these information on local storage we usually use some syntax of its like:
    
    ```Javascript
        localStorage.setItem('fullname', 'Vu Hai Nam');
    ```
    
    An interesting of local storage is just can only store the string, but for some reason I want to store more number not just only string. To deal with it, I need to create an object and change it into JSON, like this way:

    ```Javascript
        let store = {
            'fullname': 'Vu Hai Nam',
            'age': 50, 
        }

        localStorage.setItem('profile_setting', JSON.stringify(store));
        // Then we wanna add more field
        store.address = 'Ha Noi';
        localStorage.setItem('profile_setting', JSON.stringify(store));
    ```
    
    As you can see, everytime we want to add new information to store on Local-Storage we need to add new field and create another sentence of **localStorage.setItem()** and **JSON.stringify()** object it causes duplicate code. So we can use closure to deal with this situation with some short intialization at the beginning:

    ```Javascript
        function createStorage(key) {
            const store = JSON.parse(localStorage.getItem(key)) ?? {};
            function save() {
                localStorage.setItem(key, JSON.stringify(store));
            }
            const storage = {
                get(key) {
                    return store[key];
                },
                set(key, value) {
                    store[key] = value;
                    save()
                },
                remove(key) {
                    delete store[key];
                    save()
                }
            }

            return storage;
        }

        const profileSetting = createStorage('profile_setting');
        profileSetting.set('fullname', 'Vu Hai Nam');
        profileSetting.set('age', 21);

        profileSetting.get('fullname');
        profileSetting.remove('age');
    ```
    
    In the example above, because I have used closure so, in the defination of **createStorage()** function, I have defined three method inside the object storage, with this object I will have the permission in order to access the object **store**. But that is just function declareation so the scope still doesn't create.

    But I have called the function and assigned it to **profileSetting** variable. In addition, we need to pay more attention here, because the function **createStorage** ***return*** the **storage** object, and create **storage** object by using parse JSON file on localstorage. Because of returning, so **profileSetting** is the object, then I call **set()** method in order to create new field. 

    You can see here, in the **set()** method, the scope of this block or this function doesn't include **save()** method, so it will move out of its scope and find out the **save()** method at outer (that's called closure). Futhermore, the **save()** method have defined setItem and stringify sentence so we just only need to pass the key and value to **set()** method. With this solution we can save lots of time whenever we want store data at Local-Storage by using clouser.

    - Another interesting of clouser I have mentioned above is to show the private property of OOP, right? Ok, let consider another example:

    ```Javascript
        function createApp() {
            let cars = [];
            return {
                add(car) {
                    cars.push(carr);
                },
                show() {
                    console.log(cars);
                }
            }
        }
        
        const app = createApp();
        app.add('BMW');
        app.add('Mercedes s450') 
        app.show()    // Expected output: ["BMW", "Mercedes s450"]
    ```

    The example above is to imagine that we want create an application which can management at a basic level like add cars and show list of them, so I have declared **createApp()** function and return an object with two method then assign them for **app** variable. As you can see, we can add a car named BMW and another car named Mercedes then use **show()** method to display the list. At both function **add()** and **show()** we dont see the array **cars** but it is still working based on the ability of closure, then both function have move out their scope, and find **cars** array. 

    Because determining there are only two functions can be able to have ability to access **cars** list. Unless public both function, we cannot access **cars** array (Local scope) it will throw an error. 

    ```Javascript
        console.log(cars)  //Uncaught ReferenceError: cars is not defined at ...
    ```

    - It's time to look back the third point which is mentioned at Scope topic above. Let reuse the previous example, **cars** array is the local scope so we can not access at out side, Right? But call its parent function so the **cars** array is created, imagine there is no return sentence at function declaration sentence, the array will be created but when the function ends, it also will be released out of memory. However, I have returned and assigned object to **app** global variable, and fortunately, globale variable wii be removed when the program enxits

    At that time, the global **app** will keep the object which includes **add()** and **show()**
    function into memory. And with the both function they reference to the array at outer scope, so when the function executed succesfully:

    ```Javascript
        const app = createApp();
    ```

    The result of function still keeping by **app** variable. In conclusion, the **app** global variable is the main reason that makes local variable in **creatApp()** function is not deleted from memory.

- Hoisting (60%)

    ### Defination
    
    - It is a concept when we declare a function or variable, the Javascript engine will hoist this declaration at the scope.

    1. Hoisting with "**var**", "**function declaration**"
       - For instance:

       ```Javascript
            console.log(age);   //Expected Output: underfined
            var age = 21;
        ```

        As thinking of logic, we will think the output might be **is not defined** but the result is different. The defination of hoisting will pick the declaration up and place it down at beginnign of scope like this:

        ```Javascript
            var age;
            console.log(age);
            age = 21;
        ```

        Because **age = 21** is assignation, so there is only **var age** declaration will be hoisted. and after assigning statement we can log this variable without error. How about with function declaration? Consider the next example:

        ```Javascript
            console.log(sum(5, 5))   //Expected Output: 10
            function sum(a, b) {
                return a + b;
            }
        ```
        As you can see here we are using and logging the result of **sum()** function before initializing it. It pretty same with var, but for function it will hoist all the function declaration block.
    
    2.  Hoisting with "**let**", ""**const**"
        - Maybe, we've already heard that **let** and **const** are not hoisted, it is correct. Both of them still can hoist but it kinda different than **var** and **funcition** so sometimes, it makes some understanding:

        ```Javascript
            console.log(name);      //ReferenceError: Cannot access 'name' before initialization
            let name = 'Nam';
        ```

        For **var**, it is hoisted and assign with default value is undefine, and for **let** and **const** are also hoisted but the only different here is both of them does not create default value and they are placed at ***Temporal Dead Zone*** (The area is temporarily unusable) like this:

        ```Javascript
            let name;               //Temporal Dead Zone
            console.log(name);
            name = 'Nam';

    - So what is the purpose of using Hoisting? To hoist the declaration in order to make sure that the statement inside the block does not need to move out of scope like this:

    ```Javascript
        {
            let fullName = 'Nguyen Van B';
            {
                let fullName = 'Nguyen Van A';
                {
                    console.log(fullName);
                    let fullName = 'Vu Hai Nam';
                }
            }
        }
    ```

- Value Types & Reference Types (60%)
    
    ### Defination

    - Basically, there are two types in Javascript: value types and reference type:

        | Value Types | Reference Types |
        | ----------- | -----------     |
        | String      | Object          |
        | Number      | Array           |
        | Boolean     | Function        |
        | Symbol      |                 |
        | Undefined   |                 |
        | Null        |                 |

    ### Applycation

    - With value types we can say that is primative data type, that means if we assign this type with value the type will store exactly this value. At one time, these primative data types will store only one value. For example:

    ```Javascript
        let a = 1;
        let b = 1;
        a = 2;
        console.log(b);  //Expected Output: 1
    ```
    With **let a = 1**, Javascript write command to create **a** variable then tell the memory in order to provide a data memory cell.

        | Variable    | Value       | Data memory cell |
        | ----------- | ----------- | ---------------- |
        | a           | 1           | 1                |

    With **let b = a**, Javascript write command to create **b** variable then provide another data memory cell and copy the **value of a**

        | Variable    | Value       | Data memory cell |
        | ----------- | ----------- | ---------------- |
        | a           | 1           | 1                |
        | b           | 1           | 1                |

    With **a = 2**, that means value and data memory cell **a** will change, and **b** is not:

        | Variable    | Value       | Data memory cell |
        | ----------- | ----------- | ---------------- |
        | a           | 2           | 2                |
        | b           | 1           | 1                |

    For example above, **a** and **b** are provided two different data memory cell, so changing the value of **a** does not make the changing at **b** because they have different data memory cell.

    - With reference types, changing the value at **a** function/array/object will make change at **b**. Let's consider the example below:

    ```Javascript
        let a = {
            name: 'Honda',
        };
        let b = a;
        a.name = 'Toyota';

        console.log(b)          //Expected Output: {name: "Toyota"}
    ```

    With **let a = {name: 'Honda'}**: Create **a**, provide a data cell, store **{name: 'Honda'}** into a data cell, return the index and assign it to **a**
        | Variable    | Value       | Index      | Data memory cell |
        | ----------- | ----------- | ---------- | ---------------- |
        | a           | <#001>      | #001       | {name: 'Honda'}  |

    With **let b = a**: Create **b**, point the **b** to index of **a** variable:

        | Variable    | Value       | Index      | Data memory cell |
        | ----------- | ----------- | ---------- | ---------------- |
        | a           | <#001>      | #001       | {name: 'Honda'}  |
        | b           | <#001>      |            |                  |

    With **a.name = 'Toyota'** that means change the value at data cell, because **b** variable pointed to index of **a** so the changing at **a** variable here is the same effect with **b** by the same index

        | Variable    | Value       | Index      | Data memory cell |
        | ----------- | ----------- | ---------- | ---------------- |
        | a           | <#001>      | #001       | {name: 'Toyota'} |
        | b           | <#001>      |            |                  |