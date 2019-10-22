## Hoisting 

* Variable declaration and function declaration are processed before any code is executed. 
* So declaring code or function anywhere in the
code is equivalent to declaring at the top.
* So variables and functions can appear to be used before even they were declared this behaviour is called hoisting.
* Only variable declaration are hoisted to the top and not variable defintion
* To better understanding please refer to the examples below.
```
console.log(definedLater);
var definedLater;  // variable declaration is hoisted to the top
definedLater = "I am defined";
console.log(definedLater);

Output: undefined
I am defined
```
```
console.log(definedSimultaneously);
var definedSimultaneously = "I am defined"; //variable declaration is hoisted to the top and not definition.
console.log(definedSimultaneously);

Output: undefined
I am defined
```
* Function declaration
```
myFunc(); // Function declaration is hoisted to the top
function myFunc(){
	console.log("Function executed");
}

Output: Function executed
```
```
func() // function is defined to the func variable in the below line so func() is not recognized as function in this line 
var func = function(){
	console.log()
}

Output: Uncaught TypeError: func is not a function.
```


