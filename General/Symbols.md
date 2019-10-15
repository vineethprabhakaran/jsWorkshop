## Symbols

* Symbols are a new datatype in ES6. 
* A Symbol is a unique immutable data type. They are tokens used as unique Id's.
* Symbols are always unique.
* Symbols can be created by the factory symbols method `Symbol()` as shown below.

```
let symbol1 = Symbol();
let symbol2 = Symbol('symbol2') // the text used inside the parenthesis is used to identify the symbol

console.log(symbol1 === symbol2);

Output: false
```
* Since symbols are unique creating symbols with same name will also always be false.
```
let symbol01 = Symbol('symbol02');
let symbol02 = Symbol('symbol02');

console.log(symbol01 === symbol02);

Output: false
```
* When we add symbol with a string it will give a type error so before adding we need to add the `toString()`` method 

```
let symbol1 = Symbol("symbol02");
console.log("Symbol: "+ symbol1.toString());

Output: Symbol: Symbol(symbol02)
```

### Uses of Symbols

* Symbols can be used as property keys.
```
const MY_KEYS = Symbol();
let obj = {};
obj[MY_KEYS] = 100;
console.log(obj[MY_KEYS]);

Output: 100
```
* Symbols can be used to represent constants
```
const COLOR_RED = Symbol('RED');
```
