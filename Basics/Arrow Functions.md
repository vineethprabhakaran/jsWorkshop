## Arrow functions 

* An arrow function has a shorter syntax then normal function and does not bind its own this.
* These functions expressions are best suited for non method functions.
* Below are some of the syntax of how to write arrow functions.
```
(param1, param2) =>{ statement }
(param1, param2) => expression // using expression without the curly braces will return the expression.
(param1, param2) =>{ return expression; } // this is equivalent to the above line.

(singleParam) =>{ statements } // parenthesis are optional when there is only one parameter.
singleParam =>{ statements } // this is equivalent to the above line.

() =>{ statement }
() =>{ expressions }
() =>{ return expression }
```
* Examples of an arrow function
```
// Normal Function 
var multiply = function(x, y){
	return x * y;
}

// Arrow Function 
var multiply = (x, y) => { return x*y };
// or 
var multiply = (x, y) => x*y;
```
* Arrow functions works better with higher order functions like map and reduce functions.
```
var alphabets = ["Apple","Ball","Cat","Dog","Eagle"];
// Map function which takes normal function as argument
var alphaLength = alphabets.map(function(letters){
	return letters.length;
});

// Map function which takes arrow function as argument
var alphaLength1 = alphabets.map((letters) => {return letters.length;});

var alphaLength1 = alphabets.map(letters => letters.length );
```
* Until arrow functions every new functions defined its own this value.Arrow functions does not create its own this contest.
* So this has a original meaning from its enclosing contest.
```
function Person(){
	this.age = 0;

	setInterval(()=>{
		this.age++; // In a normal function this here is going to refer to the global object but here in the person object it is going to refer to the person object.
	},1000);
}

var p = new Person();
```
### Returning Object literals
* Whenever we are going to return an object we need to enclose the object within parenthesis as shown below.
```
var func = ()=>({foo:1});
```

