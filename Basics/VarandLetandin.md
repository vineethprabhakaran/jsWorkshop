## Var Vs const Vs let 

* **const** : It is for values that never change.
```
const pi = 3.14; // we cannot change the value of this variable

```
* **let** : let is for block level variables
```
//console.log(i); we cannot access i outside the block of the for loop
for(let i = 0; i < 3; i++){
	console.log(i);
}
//console.log(i);

Output: 0
1
2
```
* **var**: var is available to variables for an entire function or to an entire program
```
console.log(i); // using var this will be undefeined which means it is declared and not defined.
for(var i = 0; i < 3; i++){
	console.log(i);
}
console.log(i); // this will also have a value 3.

Output: undefined
0
1
2
3
```
