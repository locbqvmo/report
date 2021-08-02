## Nguyen Thi My 
- Scope : scope of a variable 
**Globa scope**
- global scope
- local scope

var a=12
function sum(){
    b=20
}
sum();

-  b is restricted to function sum when the sum function is executed.
- a outside the function is called golbal scope

var a=12
function sum(){
    b=20;
    console.log(a)
    console.log(b)
    <!-- output 12 -->
     <!-- output 20 -->
}
sum();

- access a (golbal scope) into the function sum (local scope)

var a=12
function sum(){
    b=20;
    console.log(a)
 
}
console.log(b)
<!-- output b is not define -->
sum();
- b scope of operation is only in function sum
