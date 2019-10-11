## Immediately Invoked Function Expression (IIFE)
* IIFE is a javascript function which runs as soon as it is defined.
```
 (function(){
 	console.log("IIFE");
 })();

Ouput: IIFE
```
* We can also provide name to IIFE and call it explictly as below.

```
(getNumber = function(num = 3){
	console.log("The number is "+num);
})();

getNumber(5);

Output: The number is 3
The number is 5
```
* The most important function of IIFE is to avoid clearing of variables in the global scope and to create closures.
* Many javascript libraries use this technique so that variable names don't conflict between library and the program using those library.
* Below is a simple example.

```
var a = 25;
(function(){
 var a = 2;
 console.log(a);
})();
console.log(a);

Output: 2
25
```
* In ES6 you can achieve IIFE using block scope as shown below.
```
var b = 25;
(function(){
 var b = 2;
 console.log(b);
})();
console.log(b);

Output: 2
25
```
