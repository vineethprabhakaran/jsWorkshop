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
