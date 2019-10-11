## Random Numbers

In Javascript we can generate a random number as below.
```
console.log(Math.random());

Output: 0.0897523216912175
```
We can generate random numbers within 20 i.e. from 0 to 19 as below.
```
console.log(Math.floor(Math.random() * 20));

Output: 15
```
We can generate random numbers between two number where the two numbers are inclusive.
```
function randomNumber(min,max){
	var ran = Math.random();
	return Math.floor(ran * (max - min +1 )) + min;	
}
console.log(randomNumber(1,9));

Output: 5
```
