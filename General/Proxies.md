## Proxies

* Proxies are used to defined custom behaviour when the properties of the returned objects are accessed.
* Syntax : var a = new Proxy(target,handler)
* target - object 
* handler - explains how it is going to be different than the usual objects. The methods in the handler are called traps.
```
var handler = {
	get (target , key){
		return key in target ? target[key] : 37
	}
};


var p = new Proxy({}, handler);
p.a = 1
p.b = undefined;
console.log(p.a, p.b);
console.log('c' in p , p.c);

Output: 1 undefined
false 37
```
* Noraml objct without proxy

```
var p1 = {};
p1.a = 1
p1.b = undefined;
console.log(p1.a, p1.b);
console.log('c' in p1 , p1.c);

Output: 1 undefined
false undefined
```
