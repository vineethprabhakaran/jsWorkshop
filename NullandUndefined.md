## null Vs Undefined
* *Undefined* It means a variable is declared but not defined.

The following code snippets explains the difference between null and undefined.
```
var a;
console.log(a);
Output: undefined
```
```
a = null;
console.log(a);
Output: null
```
```
console.log(null == null);
Output: true
console.log(null === null);
Output: true
console.log(undefined == undefined);
Output: true
console.log(undefined === undefined);
Output: true
console.log(null == undefined);
Output: true
console.log(null === undefined);
Output: false
console.log(20 + null +1);
Output: 0
console.log(1 + undefined);
Output: NAN
```
