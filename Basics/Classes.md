## Javascript Classes

* In Javascript classes are a blue print from which objects can be created and classes are created in javascript as below.
```
class Person{
	constructor(name,year_of_born){
		this.name = name;
		this.year_of_born = year_of_born;
		console.log("Person Constructor initialized");
	}

	get Age(){
		return new Date().getFullYear() - this.year_of_born;
	}

	what(){
		console.log(this.name+" is a Person");
	}
}

var me = new Person("XYZ", 1993);
me.what();
console.log(me.Age);

Output: Person Constructor initialized
XYZ is a Person
26
```
* In classes we can use inheritance and super property as below. Compare the output of the above and the below programs.
```
class Juggler extends Person{
	what(){
		super.what();	
		console.log(this.name+" is a Juggler");
	}
}

var you = new Juggler("John",1983);
me.what();
you.what();

Output: Person Constructor initialized
XYZ is a Person
John is a Person
John is a Juggler
```
### Class Expressions
* In javascript we can also create classes using class expressions.
* Class expressions is of two types and they are `named` and `unnamed`

#### Named class expression
* In javascript we can create named class expressions as show below.
```
var nm = class Person1{
 	constructor(name,year_of_born){
		this.name = name;
		this.year_of_born = year_of_born;
	}

	what(){
		console.log("Named class Expressions by "+ this.name);
	}
 }

 var named =  new nm("John",2000);
named.what();

Output: Named class Expressions by John
```
#### Un-named class expression
* In javascript we can create named class expressions as show below.
```
var un = class{
	constructor(name,year_of_born){
		this.name = name;
		this.year_of_born = year_of_born;
	}

	what(){
		console.log("Unnamed class Expressions by "+ this.name);
	}
}

var unnamed =  new un("Sarah",2000);
unnamed.what();

Output: Unnamed class Expressions by Sarah
```

