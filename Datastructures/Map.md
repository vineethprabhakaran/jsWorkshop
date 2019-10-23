## Maps in Javascript
* A map is a datastructure in javascript which stores data in key value pairs.
* By default objects are maps as it stores values in key value pairs.
* Below is the implementation of a map using objects in javascript.
```
let map1 = function(){
	this.collection = {};
	this.count = 0;

	this.size = function(){
		return this.count;
	}
	this.set = function(key, value){
		this.collection[key] = value;
		this.count++;
	}
	this.has = function(key){
		return (key in this.collection);
	}
	this.get = function(key){
		return (key in this.collection)?this.collection[key]:null;
	}
	this.delete = function(key){
		let del = null;
		if(key in this.collection){
			del = this.collection[key];
			delete this.collection[key];
			this.count--;
		}
		return del;
	}
	this.values = function(){
		let result = new Array();
		for(let key of Object.keys(this.collection)){
			result.push(this.collection[key]);
		}
		return result;
	}
	this.clear = function(){
		this.collection = {};
		this.count = 0;
	}
}

let map = new map1();
map.set("one",1);
map.set("two",2);
console.log(map.has("one"));
console.log(map.get("one"));
console.log(map.values());

Output: true
1
[1,2]
```
### Map object
* The map object was introduced in javascript in es6
* The example of an map object is shown below.
```
let map3 = new Map();
map3.set("one",1);
map3.set("two",2);
console.log(map3.has("one"));
console.log(map3.get("one"));
console.log(map3.values());
console.log(map3.entries());

Output: true
1
MapIterator {1, 2}
MapIterator {"one" => 1, "two" => 2}
```
### Differences between Object Vs Map

* An object is a prototype so there are default keys in a map that could colloide with your keys.
* Object keys can be strings or symbols but keys of a map object can be functions, strings, boolean, numbers or even not a number(NAN).
* We can get the size of a map object easily with the size property while the size of the object must be determined manually.
