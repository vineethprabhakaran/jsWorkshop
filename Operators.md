## Logical operators and Short Circuit Evaluation
### Logical operators &&(AND) and ||(OR)

Let's consider the following functions for true and false scenarios.
```
var test = true;
var isTrue =  function(){
	console.log("This is True");
}
var isFalse = function(){
	console.log("This is false");
}
```
When test is in true scenario the function isTrue can be called as below.
```
if(test){
	isTrue();
}
```
We can write the above 'if' statement in a better way as below.
This is know as **Short Circuit Evaluation**.
```
(test && isTrue());

(!test || isFalse());
```
We can use logical OR to set a default values to variable.
```
function setName(name){
	name = name || 'XYZ';
	console.log("My Name is "+ name);
}
setName();
setName("Batman");

Output: My Name is XYZ
Output: My Name is Batman
```

## Ternary Operator

*Syntax* : (condition) ? (execute if condition is true) : (execute if condition is false)
```
function setName(name){
	name = name || 'XYZ';
	console.log("My Name is "+ name);
}
setName() ? setName(): setName('Superman');

Output: My Name is XYZ
Output: My Name is Superman
```
