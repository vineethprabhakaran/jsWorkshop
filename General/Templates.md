## Template Literals

* Template literals are string literals allowing embedded expressions.
* Template Literals are represented by using the back-tick(`) character
* Template literals are used for
  * Multi-line strings
  * expression interpolation
  * Tagged Template literals
  
### Multi-line strings

```
console.log(`string line 1
	string line 2`);
  
Output:
string line 1
	string line 2
```
### Expression Interpolation	
* In expression interpolation we can inject the expression into the string literal.
```
x = 10
y = 5
console.log(`Here is fifteen ${x + y} and \nfifty ${x * y}`);

Output: 
Here is fifteen 15 and 
fifty 50
```
### Tagged Template literal

* Tagged Template literal is passing a template literal into a function.

```
function tag(string, ...content){

console.log(string);
console.log(content);

return "TEMPLATE";
}

tag`Here is fifteen ${x + y} and fifty ${x * y}`; // Return value is TEMPLATE

Output:
["Here is fifteen ", " and fifty ", ""]
[15,50]
```

* Tagged Template literal can be used for complex scenarios like below.

```
function template(strings, ...keys) {
	console.log(strings);
	console.log(keys);
  return (function(...values) {
  	console.log(values);
    var dict = values[values.length - 1] || {};
    var result = [strings[0]];
    keys.forEach(function(key, i) {
      var value = Number.isInteger(key) ? values[key] : dict[key];
      result.push(value, strings[i + 1]);
    });
    return result.join('');
  });
}

var t1Closure = template`${0}${1}${0}!`;
t1Closure('Y', 'A');  // "YAY!"
var t2Closure = template`${0} ${'foo'}!`;
t2Closure('Hello', {foo: 'World'});  


Output:
"Hello World!"
```
