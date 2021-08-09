# 05/08

## Javascript

**Async and Performance**

**JSON** : (JavaScript Object Notation) is a data format. Hence languages exchange data through json format . JSON : Number, Stirng, Boolean, Null, Object

        Ex: 
        var json = '{"name": "Tien Viet","age":22}'

> - Stringify : Js -> JSON

        Ex :
        console.log(JSON,stringify([
            name : 'Tien Viet',
            age: 22
        ]))

> - Parse : JSON -> Js

        Ex:
        var a = '1'
        console.log(JSON.parse(a))

**Callback** : is a function passed as an argument when calling another function

        Ex:
        function myDisplayer(some) {
                document.getElementById("demo").innerHTML = some;
        }

        function myCalculator(num1, num2, myCallback) {
                let sum = num1 + num2;
                myCallback(sum);
        }

        myCalculator(5, 5, myDisplayer);

> - Use a Callback when : 
> - + Handle async
> - + A function depends on the return of another function
> - + One function needs to run after another

> - Consequences of abusing callbacks : Callback hell

        Ex : 
        
        function getup(viecnaodo){
                viecnaodo();
        }
        function cleanMyteeth(viecnaodo){
                viecnaodo();
        }
        function eat(viecnaodo){
                viecnaodo();
        }
        function main(){
                getup(function(){
                        cleanMyteeth(function(){
                                eat(function(){
                                        console.log('OMG!!!!');
                                });
                        });
                });
        }

**Asynchronous** : Run the code by priority 

        Ex:

        console.log(1)
        setTimeout(function(){
                console.log(2)
        },1000)
        console.log(3)

        /////////////////
        1
        3
        2 