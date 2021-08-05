## Nguyen Thi My

 **Callback**
 - Is a function.
 - passed as argument.
 - called again (in the function that takes arguments).

function MyFunction(param){
     console.log("123");
     param("Nguyen Thi My")
};
function callback(value){
console.log("Value":value);
}
MyFunction(callback);

**Promise**
- Promises are a mechanism in JavaScript that helps you execute asynchronous tasks without falling into callback hell or pyramid of doom, which is a situation where callback functions are nested at too many layers.

const promise = new Promise((resolve, reject) => {
    const question = confirm('True or Dare');

    if (question) {
        return resolve('Dare')
    } else {
        return reject('True')
    }
})

promise
    .then(result => {
        console.log(result);
    })
    .catch((error) => {
        console.error(error);
    })
    .finally(() => {
        console.log("Finally!!!")
    })


