## Nguyen Thi My
**Ajax**
- AJAX is an acronym for Asynchronous JavaScript and XML. It is a set of web design techniques that make web applications work asynchronously – handling all requests to the server from the back end.
Asynchronous, JavaScript, XML in the word AJAX is:
+ Asynchronous, or in short, Async – asynchronous. Asynchronous means that a program can process functions non-sequentially, has no processes, can skip some steps. The most obvious of asynchronous is that the program can process many work at once.
+ XML is a form of markup language like HTML, its full text is eXtensible Markup Language. If HTML is used to display data, XML is designed to hold data.


|| Browser              ||  -------->          || Server            ||  -------> || Browser               || 
|| call event           ||                     ||                   ||           ||                       ||
|| create XMLHTTPRequest||  -------->          ||handle Httprequest ||  -------> ||get response           ||
|| Send HttpRequest     ||                     ||return response    ||           ||handle and update view ||

var url ="http://product 1...." //declare the address and where to get server data.
var xhr = new XMLHttpRequest //initialize  object XMLHttpRequest
xhr.send();

**Callback**

- Nested/Chained Callbacks
- Consider:

listen( "click", function handler(event){
	setTimeout( function request(){
		ajax( "http://some.url.1", function response(text){
			if (text == "hello") {
				handler();
			}
			else if (text == "world") {
				request();
			}
		} );
	}, 500) ;
} );

First (now), we:

listen( "..", function handler(event){
	// ..
} );

Then later, we:

setTimeout( function request(..){
	// ..
}, 500) ;

Then still later, we:

ajax( "..", function response(..){
	// ..
} );

And finally (most later), we:

if ( .. ) {
	// ..
}
else ..


**ES6 & Beyond**
- Block-Scoped Declarations:
var a = 4;

(function sum(){
	var a = 3;
	console.log( a );	// 3
})();

console.log( a );		// 4

- let Declarations:

let a = 2;

if (a > 1) {
	let b = a * 3;
	console.log( b );		// 6

	for (let i = a; i <= b; i++) {
		let j = i + 10;
		console.log( j );
	}
	// 12 13 14 15 16

	let c = a + b;
	console.log( c );		// 8
}
let operates within a block, reassigning the value

const Declarations:

{
	const a = 2;
	console.log( a );	// 2

	a = 3;				// TypeError!
}
const operates within a block, the value cannot be changed

- Spread