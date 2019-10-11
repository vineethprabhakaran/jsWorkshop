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
