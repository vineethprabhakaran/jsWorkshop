## Closures
* A closure is a combination of the function and the environment within which it was decalred.
* In Javascript the function consists of variables whose scope exists within the function when closures are not available.
* One main use of closures is that, we can create private methods and access them by using other methods. So that the variables and the methods remain can remain private as shown below.
```
var counter = (function(){
var privateCounter = 0;
function changeBy(val){
privateCounter += val;
}

return{increment:function(){
	changeBy(1);
},
decrement: function(){
	changeBy(-1);
},
value:function(){
	return privateCounter;
}
};
})();

console.log(counter.value());
counter.increment();
counter.increment();
console.log(counter.value());
counter.decrement();
console.log(counter.value());

Output: 0
2
1
```
