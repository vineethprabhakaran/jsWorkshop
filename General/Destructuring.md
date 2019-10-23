## Destructuring 

* Destructuring assignments is a javascript syntax that makes it possible to extract data from arrays or objects into distinct variables.

### Assigning varibles from objects 

* The old way to assign variable from objects is like,
```
var voxel = {x:3.14, y:7.4, z:6.5};
 
 var x = voxel.x;
 var y = voxel.y;
 var z = voxel.z;

 console.log(x,y,z);

 Output: 3.14 7.4 6.5
```
* We can do the same thing above with destructuring like,
```
const{x ,y ,z} = voxel;
console.log(x,y,z);
Output: 3.14 7.4 6.5
```
or we can do like
```
const{x:a, y:b, z:c} = voxel; // Here x, y, z will get the x, y, z value from the object and assign it to a,b,c respectively
console.log(a, b, c); 
Output: 3.14 7.4 6.5
```
### Assigning variables from nested objects.
```
const nest = {
	start:{x: 5,y:6},
	end:{x:7,y:8}
};

const{start:{x:startX}, end:{x:endX}} = nest;
console.log(startX, endX);

Output: 5 7
```
### Assigning variables from arrays
```
const[q, r] = [1,2,3,4,5]; //q and r gets the values of first two elements in the array.
console.log(q,r);
Output: 1 2
```
* We can also access values of any index by structuring using number of commas to reach the index.
```
const[s,,,t] = [1,2,3,4,5];
console.log(s,t);
Output: 1 4
```
### Rest operator to reassign array elements
```
const[m, n, ...rest] = [1,2,3,4,5,6];
console.log(m,n); // assigns the first two elements to m and n 
console.log(rest); // The remaining part of the array gets assigned to the rest variable.
Output: 1 2
[3,4,5,6]
```
### Pass an object as a function parameter
* We can use destructuring to pass an object as a functions parameter.
```
const profile = ({name,age,nationality})=>{ // here we are performing destructuring inside the parenthesis and we can only pass specific values from the object to the function 
// do something here 
}
```
