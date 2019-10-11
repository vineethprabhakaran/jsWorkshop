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
