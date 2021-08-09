# 05/08

## Javascript

**Async and Performance**

**Promise** : Handle Async, handle Callback hell, clean code

> - Concpect : 

        var promise = new Promise(
                function(resolve,reject){
                        // logic
                        // success : resolve()
                        // fail : reject()
                }
        );

        promise
                .then(function(){

                })
                .catch(function(){

                })
                .finally(function(){

                })

> - Promise have 3 status :

> - + Pendding : When func in Promise wait for reslove or reject 

        Ex:

        var promise = new Promise(
                function(resolve,reject){
                        /// code here
                }
        )

> - + Fulfilled : WWhen func in Promise be  successfully executed 

        Ex:

        var promise = new Promise(
                function(resolve){
                        resolve(123)
                }
        )

        promise.then(function(result){
                console.log(result)
        )}

> - + Rejected : When func in Promise be Failded

        Ex: 

        var promise = new Promise(
                function(reject){
                    reject("Error")
                }
        )
        promise.catch(function(error){
                console.log(error)
        })

> - Handle Async

        Ex : 

        function mot(){
            return new Promise((resolve,reject)=>{
                setTimeout(() =>{
                    resolve("mot")
                },1000)
            })
        }
        function hai(){
            return new Promise((resolve,reject)=>{
                setTimeout(()=>{
                    resolve("hai")
                },2000)
            })
        }
        function hello(){
            return new Promise((resolve,reject)=>{
                resolve("Hello world")
            })
        }

        mot()
        .then(function(data){
            console.log(data)
            return hai()
        })
        .then(function(data){
            console.log(data)
            return hello()
        })
        .then(function(data){
            console.log(data)
        })
        .catch(()=>{
            console.log("Error")
        })


**Generator function** : Generators are functions which can be exited and later re-entered. Their context (variable bindings) will be saved across re-entrances

> - Syntax :

        function* name([param[, param[, ... param]]]) {
            statements
        }

>  - Return Value : iterator object

        Ex :

        var it = {}; // iterator
        it.next = function(){
            var r = { value: 5, done: false }; // iterator result
            return r;
        };

> - Yeild : is the keyword used to pause and also to resume the execution inside the generator function 

        Ex : 

        function* generatorFunc(index) {
        while (index < 2) {
            yield index++;
        }
        }

        const iterator = generatorFunc(0);

        console.log(iterator.next());
        // log output: {value : 0, done : false}

        console.log(iterator.next());
        // log output: {value : 1, done : false}

        console.log(iterator.next());
        // log output: {value : underfined, done : true}

**Async/await** : is a special syntax that lets you declare that a function will perform an asynchronous action. Await to declare waiting for the result of an asynchronous operation inside an action with the async keyword  

> - Syntax :

        async function getSomeAsyncData(value){
            const result = await fetchTheData(someUrl, value);
            return result;
        }

>        Ex : 

        async function fetchTheFirstData(value){
            return await get("someUrl", value);
        }
        async function fetchTheSecondData(value){
            return await getFromDatabase(value);
        }
        async function getSomeData(value){
            try {
            const firstResult = await fetchTheFirstData(value);
                const result = await fetchTheSecondData(firstResult.someValue);
                return result;
            }
            catch(error){
                // Every error thrown in the whole “awaitable” chain will end up here now.
            }
        }

**fetch** : is method call Api for get data, Written based on the property of Promise

        Ex :

        file Js :
        var postApi = "https://jsonplaceholder.typicode.com/posts"

        fetch(postApi)
        .then(function(response){
            return response.json();
        })

        .then(function(posts){
            var htmls = posts.map(function(post){
            return `<li> 
                    <h2> ${post.title} </h2>
                    <p> ${post.body} </p>
            </li>`;
            })
            var html = htmls.join('')
            document.getElementById('post-block').innerHTML = html
        })

        file html: body :
        <ul id = "post-block"></ul>

**REST API** : REST stands for REpresentational State Transfer. This is a web standard based on the HTTP protocol. The main purpose of REST is to support resource access via HTTP protocol 

> The job of a REST server is simply to provide access to resources, a REST client will use those access rights to obtain resources, all through the HTTP protocol. Resources are identified through the URI. REST uses 2 data formats, JSON and XML, but JSON is more popular 

> REST Api : action definition, based on HTTP protocol . 
> HTTP protocol provide methods to work with data 

        Ex: 

        POST : new data
        GET : get data
        PUT : fix data
        DELETE : delete data

**Template Literals** : use `` for data transmission

        Ex:

        const courseName = 'Javascript';
        const description = `Course name : ${courseName}`

**Default parameter values** : use to variable we know value's variable . 

        Ex:

        function logger(log,type = 'log'){
            console[type](log);
        }

        logger('Message...')

**Enhanced object literals** : 
> - Defind key: value for object
> - Defind method for object

        Ex :

        var name = 'Javacript';
        var price = 1000;

        var course = {
            name,
            price
            getName(){
                return name;
            }
        };
        console.log(course) // course{name: 'Javacript',price = 1000 }
        console.log(course,getName())

**Destructuring** : 
> - Destructuring Array : get elements in array 

    Ex: 
    var array = ['mot','hai','ba']
    var [a,...rest] = array

    console.log(a) // mot
    console.log(rest) // ['hai','ba'] 

> - Destructuring Object : 

    Ex : 
    var number = {
        mot: 'mot'
        hai: 'hai'
        ba: 'ba'
    }
    var {mot,hai...rest} = number
    console.log(mot,hai);// mot, hai
    console.log(rest): // {ba}

**Spread** : how to get the value inside object or array

    Ex: 
    var defaultConfig = {
        api: 'abcxxyz',
        apiVersion: 'v1',
        other: 'ohter'
    }   
    var exerciseConfig = {
        ...defaultConfig,
        api:'xyzabc'
    };
    console.log(exerciseConfig);

