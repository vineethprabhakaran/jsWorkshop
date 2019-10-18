## Spread and Rest operator

### Spread Operator

* Spread operator allows expresssion to be expanded in places where multiple areguments, elements or variables are expected.
* Uses of spread operator are
	* add elements of an existing array into a new array.
	* pass elements of an array as arguments to a function.
	* copy arrays
	* concat arrays


* add elements of an existing array into a new array.
```
var array1 = [1,2,3];
var array2 = [4,...array1,5,6];
console.log(array2);

Output: [4, 1, 2, 3, 5, 6]
```
* pass elements of an array as arguments to a function.
```
function add(x, y, z){
	console.log(x + y + z);
}

var array3 = [1,2,3];
add(...array3);

Output: 6
```
* Copy arrays
```
var array4 = ['a','b','c'];
var array5 = [...array4];
console.log(array5);

Output: ["a", "b", "c"]
```
* Concat arrays
```
var array6 = [1,2,3];
var array7 = [4,5,6];

console.log(array6.concat(array7));
array6 = [...array6, ...array7];
console.log(array6);

Output: [1, 2, 3, 4, 5, 6]
[1, 2, 3, 4, 5, 6]
```

### Rest operator

* Rest operator looks exactly like the spread operator but basically its the opposite of the spread operator.
* Rest operator collects multiple elements and condense them into a single array element.
* Rest operator can be identified by its usage in the function definition.
```
function multiply(multiplier, ...theArgs){
	return theArgs.map(function(element){
		return multiplier * element;
	});
}

var result = multiply(2,1,2,3);
console.log(result);

Output: [2, 4, 6]
```
