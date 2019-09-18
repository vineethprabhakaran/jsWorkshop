# A quick deep dive into the basics of JavaScript

## Strings in Javascript
### 20 String functions:

Lets consider two strings 
```
var stringOne = "Javascript";
var stringTwo = "Javascript is best to learn";
```
* **charAt()** :Returns the character in the specified index of the string.
```
console.log(stringOne.charAt(1));
Output: a
```
* **charCodeAt()** : Returns the unicode of the character at the specified index. 
```
console.log(stringOne.charCodeAt(0));
Output: 74
```

* **concat()** : Returns the concatenated strings.
```
console.log(stringOne.concat(" "+stringTwo));
Output: Javascript Javascript is best to learn
```

* **endsWith()** : Checks if the string ends with the specified string and returns true or false.
```
console.log(stringOne.endsWith("ipt"));
Output: true
```

* **startsWith()** : Checks if the string starts with the specified string and returns true or false.
```
console.log(stringTwo.startsWith("Java"));
Output:
```

* **slice()** : Returns a part of the string. Syntax - slice(startIndex, endIndex + 1).
```
console.log(stringOne.slice(2,6));
Output: vasc
```

* **substring()** : Returns a part of the string. Works similar to the slice method.
```
console.log(stringOne.substring(2,6));
Output: vasc
```

* **substr()** : Returns a part of the string. Syntax - substr(startIndex, number of characters).
```
console.log(stringOne.substr(2,6));
Output: vascri
```

* **fromCharCode()** : Returns the character for the specified unicode.
```
console.log(String.fromCharCode(86));
Output: V
```

* **includes()** : Checks if the string have the specified string and returns true or false.
```
console.log(stringOne.includes("ee"));
Output: false
```

* **indexOf()** : Returns the starting index of the specified string.
```
console.log(stringOne.indexOf("Java"));
Output: 0
```

* **lastIndexOf()** : Returns the starting index of the specified string from the last index.
```
console.log(stringOne.lastIndexOf("a"));
Output: 3
```

* **match(regex expression)** : Returns the matching string.
```
console.log(stringOne.match("s"));
Output: s
```
* **repeat()** : Repeats the string for the specified number of times.
```
console.log(stringOne.repeat(2));
Output: JavascriptJavascript
```

* **search()** : Returns the starting index of the specified string.
```
console.log(stringTwo.search("learn"));
Output: 26
```
* **replace()** : Returns the string with the replaced substring.
```
console.log(stringOne.replace("scr","SCR"));
Output: JavaSCRipt
```

* **toLowerCase()** : Converts the string to lowercase letters.
```
console.log(stringTwo.toLowerCase());
Output: javascript is best to learn
```

* **toUpperCase()** : Converts the string to uppercase letters.
```
console.log("toUpperCase : "+ stringTwo.toUpperCase());
Output: JAVASCRIPT IS BEST TO LEARN
```
* **split()** : Returns a string array with the strings which were split by the specified delimiter. 
```
console.log(stringTwo.split(" "));
Output: Javascript,is,the,best,to,learn
```

* **trim()** : Removes spaces present only at the beginning of the sentance.
```
var spacedString = "      Javascript";
console.log(spacedString.trim());
Output: Javascript
```




## Difference between == and === 
`==`   absolute equality (Does not consider the datatype when comparing. The comparing variable will get type changed internally).

`===` strict equality.
```
console.log(3 == '3');
Output: true
console.log(3 === '3');
Output: false
console.log(true == '1'); 
Output: true
console.log(true === '1'); 
Output: false
```

String Object get converted to string literal internally so it gives true when comparing using ==
```
console.log("This is a String" == new String("This is a String"));
Output: true
```
String object is different from string literal so it will false for the below statement.
```
console.log("This is a String" === new String("This is a String"));
Output: false
```

## null Vs Undefined
* *Undefined* It means a variable is declared but not defined.

The following code snippets explains the difference between null and undefined.
```
var a;
console.log(a);
Output: undefined
```
```
a = null;
console.log(a);
Output: null
```
```
console.log(null == null);
Output: true
console.log(null === null);
Output: true
console.log(undefined == undefined);
Output: true
console.log(undefined === undefined);
Output: true
console.log(null == undefined);
Output: true
console.log(null === undefined);
Output: false
console.log(20 + null +1);
Output: 0
console.log(1 + undefined);
Output: NAN
```

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

## Arrays 
Arrays can have values of same and different datatypes.

### One-dimensional arrays.
Arrays with values of same datatype.
```
var animals = ["cat","cow","goat"];
console.log(animals);

Output: ["cat", "cow", "goat"]
```
Arrays with values of different datatype.
```
var numbers = ["Two",2,"Three",3];
console.log(numbers);
console.log(numbers[0]);
console.log(numbers[1]);

Output: ["Two",2,"Three",3]
Two
2

```
In array we can change the values using indexes.
```
var numbers = ["Two",2,"Three",3];
console.log(numbers);
numbers[2] = 3;
console.log(numbers);

Output: ["Two",2,"Three",3]
["Two",2,3,3]
```
### Multidimensional arrays

Example of multi dimensional arrays are as below.
```
var team = [["Dog",1],["Cat",2],["Cow","Three"]];
console.log(team[0]);
console.log(team[2]);

iterating the multidimensional array.
team.forEach(function(value){
	console.log(value);
	console.log(value[0]);
	
});

Output: ["Dog",1]
["Cow","Three"]
["Dog",1]
["Cat",2]
```
### Common Array Methods

Arrays have different in-built methods to perform different operations.

Lets consider the below array for the examples of array methods.
```
var arr = ["a","b","c"];
```
**push**  
* Adds a new element to the array and returns the length of the array.
* This method affects the original array.
```
console.log(arr.push("d"));
console.log(arr);

Output: 4
["a", "b", "c", "d"]
```
**pop**
* Removes the last element from the array and returns the removed element.
* This method affects the original array.
```
console.log(arr.pop());
console.log(arr);

Output: d
["a", "b", "c"]
```
**reverse**
* Reverses the array and returns the reversed array.
* This method affects the original array.
```
console.log(arr.reverse());
console.log(arr);

Output: ["c", "b", "a"]
["c", "b", "a"]
```
**join**
* Joins each element in the array into a single string with the passed argument and returns the string.
* This method doesn't affect the original array.
```
console.log(arr.join(""));
console.log(arr);

Output: cba
["c", "b", "a"]
```
**shift**
* Removes the first element from the array and returns the element removed.
* This method affects the original array.
```
console.log(arr.shift());
console.log(arr);

Output: c
["b", "a"]
```
**unshift**
* Adds a new elemnt at the start of the array and returns the length of the array
* This method affects the original array.
```
console.log(arr.unshift("c"));	
console.log(arr);

Output: 3
["c", "b", "a"]
```
**slice**
* Retuns a part of the array. Syntax : *slice(startIndex, endIndex +1)*.
* This method doesn't affect the original array.
```
console.log(arr.slice(1,3));
console.log(arr);

Output: ["b", "a"]
["c", "b", "a"]
```
**splice**
* Similar to slice but it will affect the original array and can also replace the sliced array with a new element
* Returns the sliced array 
```
console.log(arr.splice(1,3,"e"));
console.log(arr);

Output:  ["b", "a"]
["c", "e"]
```
**sort**
* Sorts the array and returns the sorted array.
* This method affects the original array.
```
arr.push("b","a","d");
console.log(arr);
console.log(arr.sort());
console.log(arr);

Output: ["c", "e", "b", "a", "d"]
["a", "b", "c", "d", "e"]
["a", "b", "c", "d", "e"]
```
**concat**
* Join two array and returns the joined array
* This method doesn't affect the original array.
```
var arr1 = ["f","g"];
console.log(arr.concat(arr1));
console.log(arr);
console.log(arr1);

Output: ["a", "b", "c", "d", "e", "f", "g"]
["a", "b", "c", "d", "e"]
["f", "g"]
```
### Copying Arrays

Arrays can be copied by using slice and spread operator.

Lets consider the below array.
```
var originalArray = [true, undefined, null,false];
```
Copying arrays using slice method. It is the common way to copy an array.

```
var copy1 = originalArray.slice(0);
console.log(copy1);
 
Output:  [true, undefined, null,false]
```
Copying arrays using spread operator

```
 var copy2 = [...originalArray];
 console.log(copy1,copy2);
 
 Output: [true, undefined, null, false]
 [true, undefined, null, false]
```
* The above methods perform shallow copy but when we want to copy an array which has an object or another array within it, 
 we have to perform deep copy.
* Shallow copy of an object and array within an array.
```
var deepArray = [["Javascript"]];
var shallowCopy = deepArray.slice(0);
shallowCopy[0].push("is great");
console.log(deepArray[0]);
console.log(shallowCopy[0]);

Output: ["Javascript", "is great"]
["Javascript", "is great"]
```
* In the above code when we try to push/add a new element "is great" into the shallowCopy[0]. 
We can see the new element is added to the deepArray[0] also.

* The reason behind this is the original array which has an array or an object within itself actually has a pointer 
which points to the inside array or object.So, when we perform shallow copy we actually copy only the pointer in the 
original array. Since both the arrays have same pointer which is pointing to the same array and when we try to add an 
new element in the inside array it will be reflected in both the array. So in order to avoid this we need to perform 
deep copy when copying arrays which has an array or object within itself.

* We need to perform deep copy as below.
```
var deepArray1 = [["Javascript"]];
var deepCopy = JSON.parse(JSON.stringify(deepArray1));
deepCopy[0].push("is great");
console.log(deepArray1[0]);
console.log(deepCopy[0]);

Output: ["Javascript"]
["Javascript", "is great"]
```


## Random Numbers

In Javascript we can generate a random number as below.
```
console.log(Math.random());

Output: 0.0897523216912175
```
We can generate random numbers within 20 i.e. from 0 to 19 as below.
```
console.log(Math.floor(Math.random() * 20));

Output: 15
```
We can generate random numbers between two number where the two numbers are inclusive.
```
function randomNumber(min,max){
	var ran = Math.random();
	return Math.floor(ran * (max - min +1 )) + min;	
}
console.log(randomNumber(1,9));

Output: 5
```
## Parsing
* **parseInt**  This method is used to string convert to Integer. 
* Syntax: *parseInt("String",base)*  `base`(2nd argument) is optional. It depicts on what base the string needs to be converted.
In the below example 11 is converted on base 2.
```
console.log(parseInt("007"));
console.log(parseInt("11",2));

Output: 7
3
```

##  Loops
* In case if you have an infinite loop your browser will get hanged so you can add the following in the address bar.
```
?turn_off_js=true
```
* if you already have a question mark add &.
```
&turn_off_js=true
```
### For Loops

* `for .. in` and `for .. of` are used to loop thorugh objects.
* `for .. in` is used to loop through property names.
* `for .. of` is used to loop through property values. It loops through iterable objects.
```
let person = {fname:"XYZ",lname:"P",arms:2};

let forOfArray = [3,7,9];
forOfArray.foo = "hello";
console.log(forOfArray);
console.log(person);

Output: [3, 7, 9, foo: "hello"]
{fname: "XYZ", lname: "P", arms: 2}
```
```
let text = "";
for(let x in person){
	console.log(x);	
	text += person[x];
}
console.log("text: "+text);

Output: fname
lname
arms
text: XYZP2

```
* The below Code loops through the property names and gives the indexes and property names of the array
```
for(let x in forOfArray){
	console.log(x + "  "+forOfArray[x]);
}

Output: 0  3
1  7
2  9
foo  hello
```
* The below code loops only the array elements not the property value within the array.
```
for(let x of forOfArray){ 
	console.log(x);
}

Output: 3
7
9
```

### 8 Array Iterations Methods

**forEach**
* In Javascript forEach loop is written as below.
```
var array = [1, 2, 3];
array.forEach(function (item,index) {
  console.log(item,index);
});

Output: 1 0
2 1
3 2
```

**map**
* It takes an item from the array and does something and puts it back in the same place in the array.
```
const three = [1,2,3];
const doubled = three.map(function(item){
	return item * 2;
});
console.log(doubled);

Output: [2, 4, 6]
```

**filter**
* It takes an item from the array and checks for an condition and puts the element back in the same place in the array if the condition is true and if it is false it not do anything.
```
const ints = [1,2,3,4,5,6];
const evens = ints.filter(function(item){
	return item % 2 === 0;
});
console.log(evens);

Output: [2, 4, 6]
```
**reduce** 
* We take an array and do something and send the result to the next iteration along with the next element.
* Syntax: `reduce(function, initial value of the result)`
```
const reducesum = [1,2,3].reduce(function(result,item){
	return result + item;
},0);
console.log(reducesum);

Output: 6
```
**some**
* Checks if any item in the array meets the condition then returns true if not false.
```
const hasNegativeNumber = [1,2,3,-1].some(function(item){
	return item < 0;
});
console.log(hasNegativeNumber);

Output: true
```
**every**
* Checks if every item in the array meets the condition then returns true if not false.
```
const allPositiveNumber = [1,2,3,-1].every(function(item){
	return item > 0;
});
console.log(allPositiveNumber);

Output: false
```
**find** 
* Checks all the matching item in the array and retuns the item if the item is found.
```
const objects = [{id:"a"},{id:"b"},{id:"d"}];
const found = objects.find(function(item){
	return item.id === "d";
});
console.log(found);

Output: {id: "d"}
```
**findIndex** 
* Checks all the matching item in the array and retuns the item's index if the item is found.
```
const objectsIndex = [{id:"a"},{id:"b"},{id:"d"}];
const foundIndex = objectsIndex.findIndex(function(item){
	return item.id === "d";
});
console.log(foundIndex);

Output: 2
```

## Objects

* In javascript an object is a standalone entity with properties and type. A property of an object can be explained as
a variable that is attached to the object.
* Properties can be accessed by dot notation and it can also be accessed by square brackets.
* Usually the properties that start with underscore, number and containing spaces within it, should be accessed by the square 
brackets.
```
var myCar = new Object();
myCar.make = "Audi";
myCar.model = "Q7";

myCar["color"] = "Red";
myCar["Do I like my car"] = "yes"; 
console.log(myCar);

Output: {make: "Audi", model: "Q7", color: "Red", Do I like my car: "yes"}
```
### Object Creation Methods
* There are three ways to create an Object and they are .
	* Object Initializer.
	* Using constructor function
	* Using Object.create() method.

**Object Initializer**
* Creating object using object initializer method.
```
var myFerrari = {color: "Red",wheels:4,engine:{cylinders:4,horsepower:2000}};
console.log(myFerrari);

Output: {color: "Red",wheels:4,engine:{cylinders:4,horsepower:2000}}
```
**Using Constructor function**
* First create the type of the object with the constructor function and then Create the instance using the new keyword.
```
function Car(make,model,year){
this.make = make;
this.model = model;
this.year =  year;
}

var myNewCar = new Car("Ferrari","sport","2000");
console.log(myNewCar);

Output: Car {make: "Ferrari", model: "sport", year: "2000"}
```
**Using Object.create() method**
* This method allow us to choose a prototype for the object without having to define a constructor function
```
var carPrototype = {type:"SUV",displayType: function(){
	console.log(this.type);
}};

var mySUV =  Object.create(carPrototype);
console.log(mySUV);

Output: {}
```
```
var mySport =  Object.create(carPrototype);
mySport.type = "Sport";
mySport.displayType();
console.log(mySport);

Output: Sport
{type: "Sport"}
```
### Using objects for lookup's
* Objects can be thought of as a key value pair storage like a dictionary.
* We can use indexes to access the objects.
```
var myAlpha = {
	1:"Z",
	2:"Y",
	3:"X"
	//...
}

console.log(myAlpha[2]);

Output: Y
```
### Removing Object Properties.
* *delete* keyword is used to delete properties in an object.
```
let dishes = {
	plates:2,
	cups: 5,
	forks: 5,
	bowls: 3
}

delete dishes.cups;
console.log(dishes);

Output: {plates: 2, forks: 5, bowls: 3}
```
### Testing objects for properties.
* *hasOwnProperty()* This method is used to determine whether the object has the specified property.
```
let dishes = {
	plates:2,
	cups: 5,
	forks: 5
}
console.log(dishes.hasOwnProperty("cups"));
console.log(dishes.hasOwnProperty("bowls"));

Output: true
false
```
### Generating array with all object keys.
* We can generate an array with the keys of an object with *Object.keys()* method.
* This method retuns an array with the properties of an objects as string in the array.
```
let dishes = {
	plates:2,
	cups: 5,
	bowls: {
		large:1,
		medium:2,
		small:3
	}
}

console.log(Object.keys(dishes));

OutputL: ["plates", "cups", "bowls"]
```
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
## Closures
* A closure is a combination of the function and the environment within which it was decalred.
* In Javascript the function consists of variables whose scope exists within the function when closures are not available.
* One main use of closures is that, we can create private methods and access them by using other methods. So that the variables and the methods remain can remain private as shown below.
```
var counter = (function(){
var privateCounter = 0;
function changeBy(val){
privateCounter += val;
}

return{increment:function(){
	changeBy(1);
},
decrement: function(){
	changeBy(-1);
},
value:function(){
	return privateCounter;
}
};
})();

console.log(counter.value());
counter.increment();
counter.increment();
console.log(counter.value());
counter.decrement();
console.log(counter.value());

Output: 0
2
1
```
## This keyword.
* The this keyword in javascript is the object that owns the javascript code.
* The value of this, when used inside a function is the object that owns the function.
* The value of this, when used in an object is the object itself.
* The value of this, when used outside the function is the global object of the javascript.
* The below code indicates that the this keyword refers to the global object.
```
console.log(this.document === document);
console.log(this === window);
this.a = 12;
console.log(window.a);

Output: true
true
12
```
* In case when this is used inside the function and the value for this is not set by the call then this will refer to the global object as shown below.
```
function func(){
	return this;
}
console.log(func() === window);

Output: true
```
* When we use *use strict* inside the function then this refers to the object within the function and it returns undefined in the below 
func() call.
```
function func1(){
'use strict'
	return this;
}
console.log(func1() === window);

Output: false
```
### Call and apply methods
* When this is used inside the function it refers to an object when is set in the call method.
* The apply method is also similar to the call method where the call method accepts the arguments as a list and the apply method accepts an array of arguments as the arguments.
```
function add(c,d){
	return this.a + this.b + c + d;
}

var o = {a:1, b:2};
console.log(add.call(o,3,4));
console.log(add.apply(o,[3,4]));

Output: 10
10
```
### Bind Method
* When we call bind method on a function  it will create a new function same as the original function and the scope.
* The this keyword is present in the orginal function and the new function will be always bound to the first argument which is passed to the bind function.
* So how many times you bind same function it will always return the same first argument as the output. 
```
function func(){
	return this.e;
}

var g = func.bind({e:"Hello"});
console.log(g());

var h = g.bind({e:"Hai"}); // will not work
console.log(h());

var f = func.bind({e:"Hai"});
console.log(f());

Output: Hello
Hello
Hai
```
### this in traditional and arrow function
* When using arrow functions this is bound to the enclosing scope at creation time  and cannot be changed.
* The bind, call and apply methods have no effect on it.
```
var O = {
	traditionalFunc:function(){
		console.log("traditionalFunc  this === O :", this === O);
		},
	arrowFunc:() => {
		console.log("arrowFunc  this === O :",  this === O);
		console.log("arrowFunc  this === window :", this === window);	
	}
}

O.traditionalFunc();
O.arrowFunc();

Output: traditionalFunc  this === O : true
arrowFunc  this === O : false
arrowFunc  this === window : true
```
* In traditionalFunc this contains value of the object when owns the function irrespective of where the function is defined.
* In arrowFunc this contains value of the global object because the arrow function which is attached to O was created in the scope of window and run in the scope of O. So this in the arrow function is bound to the window where it was created.	

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
## Strict mode
* Strict mode in javascript tightens the roles for certain behaviours and these restrictions keeps the code safe and make the javascript engine perform optimization.
* We can enable strict mode by using 'use strict' directive at the beginning of the file or using the directive at the start of the function to enable strict mode for that particular function.
```
use strict; // Enables strict mode for the entire file.

function myFunc(){
	use strict;	 // Enables strict mode for that particular function.
	y = 3.14; // this line will throw an error as this variable needs to be declared.
}

myFunc();
```
* In strict mode deleting a variable is not allowed and it is allowed in normal mode.
* In normal mode the developer will not receive any error feedback when altering non writiable properties but in strict mode it will throw an error.
* In strict mode we will get an error when we write a value in get function.
* In strict mode deleting undeletable properties will throw an error and in normal mode nothing will happen.
* In strict mode function parameter name must be unique.
* Prohibiting the use of 'with' method makes optimization better in javascript.
* Strict mode makes javascript code secure. It will not allow window to be used in a fuction using this keyword when the function is in strict mode. 

## Difference between hasOwnProperty() and in 
* hasOwnProperty returns true if the property is directly present within the object.
* in checks the property in the object and the prototype inherited by the object and returns true if the property is found.
```
var myObj = {
	name:"XYZ"
}
console.log(myObj.hasOwnProperty("name"));
console.log("name" in myObj);
console.log(myObj.hasOwnProperty("valueOf"));
console.log("valueOf" in myObj);

Output: true
true
false
true
```
## setTimeout and setInterval

* setTimeout Syntax : *setTimeout(function, milliseconds)*
* setInterval Syntax : *setInterval(function, milliseconds)*
* setTimeout is used to run a function once after the specified milliseconds.
* clearTimeout function is used to stop the setTimeout function from running.
* setInterval is used to run a function continously after the specified milliseconds.
* clearInterval function is used to stop the setInterval function when running.
* clearTimeout and clearInterval functions takes setTimeout and setInterval functions as arguments respectively. 
