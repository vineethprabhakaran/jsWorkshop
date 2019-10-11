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
