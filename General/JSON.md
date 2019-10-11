## JSON - JavaScript Object Notation
* JSON is a syntax for storing and exchanging data.
* JSON stores data in key values pairs.
* JSON accepts *Objects, Arrays, null, numbers and strings* as values and does not accept *undefined, date and functions* as values.
```
let dishes = {
	"plates":2,
	"cups": null,
	"bowls": {
		"large":1,
		"medium":"two",
		"small":3
	}
}
```
### JSON methods
**Stringify method**
* This method is used to convert the specified JSON into string.
```
var stringdishes = JSON.stringify(dishes);
console.log(stringdishes);

Output: {"plates":2,"cups":null,"bowls":{"large":1,"medium":"two","small":3}}
```
**Parse method**
* This method is used to convert a string JSON into a javascript object.
```
let dishes = '{"plates":2,"cups": 2}';

var objdishes = JSON.parse(dishes);
console.log(objdishes);

Output: {plates: 2, cups: 2}
```
### Hoisting
* Variable declaration and function declaration are processed before any code is executed. So declaring a variable and function anywhere is equivalent to  declaring at the top. This means that the variable and function appear to be used before they were declared.
This behaviour is called hoisting.
* Variable definition doesn't follow hoisting 
* In the below example the variable *definedLater* behaves as it was declared at the top and the defintion happens when the defined line is executed.
```
console.log(definedLater);
var definedLater;
definedLater = "I am defined";
console.log(definedLater);

Output: undefined
I am defined
```
* The below example also works the same way as above.
```
console.log(definedLater);
var definedLater= "I am defined";
console.log(definedLater);

Output: undefined
I am defined
```
* The below example shows that the functions was declared at the top before the function call.
```
display();
function display(){
	console.log("Function defined");
}

Output: Function defined
```

* In the below example we cannot call the function before it is defined to a variable as it will throw an error.
```
//funcVar(); uncommenting this line will through an error.
var funcVar = function(){
	console.log("Function defined");
}
funcVar();

Output: Function defined
```
