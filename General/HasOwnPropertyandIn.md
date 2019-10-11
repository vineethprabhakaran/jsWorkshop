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
