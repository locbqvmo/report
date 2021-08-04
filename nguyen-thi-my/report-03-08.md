## Nguyen Thi My
- hosting : hosting is called pull up or bring up (refers to when you declare variables, declare functions, the declarations are brought to the top of their scope
)

console.log(age);  //undefine
var a =16;

**var a** is the variable declaration . **=16** is variable assignment;

console.log(function sum(6,8)) //15
 function sum(a,b){
     return a+b;
 }


**Object**
var my ={
    name:"Nguyen Thi My",
    age:20
} 
console.log(my.name) //Nguyen Thi My

**this & Object Prototypes**
- this : this in js refers to the object it belongs to

const myInfo= {
    name:"Nguyen Thi My",
    age:20, 
    address(){
        console.log(this)
    }
}
console.log(myInfo.address) // name: "Nguyen Thi My", age: 20, address: ƒ}
address: ƒ address()
age: 20
name: "Nguyen Thi My"


- Object Prototypes : prototypes that make up an object

function User(name,age,address){
    this.name=name;
    this.age=age;
    this.address=address;
    more(){
        console.log("Hello")
    }
}
User.prototype.interest("sleep")
var user = new User("Nguyen Thi My",20,"Bac Giang");
console.log(user.interest) //sleep
