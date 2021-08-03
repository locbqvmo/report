# 02/08 
## Javascript
**Scope and Closure**

>  **Closure** : Is a function that can remember where it was created and access variables outside of it 

> Ex : 
    const nameCar = "All of car : "
    function createApp(){
        const cars = []

        return{
            add(car) {
                cars.push(car)
            }
            show(){
                console.log(nameCar)
                console.log(cars)
            }
        }
    }
    
    const app = createApp();

    app.add("Mers")
    app.add("BMW")
    app.show()

     * In the example, variable app call function add() an show() in function createApp(), func add() always remember where it was create in func createApp()

     * Func console.log(nameCar) use variable nameCar in Global, outside of show(), even outside of createApp()

> - Referenced variable in closure don't be delete form memory when function done . 
    
    After app.add("Mers") - one value be passed in array cars[], value Mers always exist in array cars[].

> - The variables declared in the function if not passed outside will always be secure and safe

    Variable cars[] in func createApp() just add value, but not delete or change value. In case, outside of createApp(), appear one valiable cars be declare with another value, variable cars[] in func createApp() still won't change type of value and value

**this & Object Prototypes**

> **Object** : is comnination of attributes or methods 

> - Attributes : about key and value
> - Method : is a funtion is initialized in object

> Ex : 

    function User(firstName, lastName){
        User.firstName = firstName;
        User.lastName = lastName;
        User.getName = function(){
            return `$(User.firstName) $(User.lastName)`
        }
    }

    * User.firstName is attributes
    * User.getname is method

> **This** : use to refers to the object to which it belongs 

> Ex :

    function User(firstName, lastName){
        this.firstName = firstName;
        this.lastName = lastName;
        this.getName = function(){
            return `$(this.firstName) $(this.lastName)`
        }
    }
    const user1 = new User('Viet','Tien')
    console.log(user1)

> - In a method, `this` reference to method access object (before `.`)

> Ex :
    
    const iPhone7 = {
        name: 'iPhone 7'
        color: 'Black'
        takePhoto(){
            console.log(this)
        }
    }

    console.log(iPhone7.takePhoto())

    * this in here is Object iPhone7

> - Outside method, `this` refer to global Object

> Ex : 

    console.log(this)

    log: Window{window: Window,seft:Window ....}

**Object Prototypes** : can add attributes outside Object

> Ex : 

    function User(firstName, lastName){
        this.firstName = firstName;
        this.lastName = lastName;
        this.getName = function(){
            return `$(this.firstName) $(this.lastName)`
        }
    }
    User.prototype.age = 23;
    User.prototype.getAge = function(){
        return this.age;
    }

> - Prototype object is shared among all ther pbjects created using new
