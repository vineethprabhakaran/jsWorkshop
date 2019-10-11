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


