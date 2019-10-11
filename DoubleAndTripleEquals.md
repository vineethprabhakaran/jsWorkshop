## Difference between == and === 
`==`   absolute equality (Does not consider the datatype when comparing. The comparing variable will get type changed internally).

`===` strict equality.
```
console.log(3 == '3');
Output: true
console.log(3 === '3');
Output: false
console.log(true == '1'); 
Output: true
console.log(true === '1'); 
Output: false
```

String Object get converted to string literal internally so it gives true when comparing using ==
```
console.log("This is a String" == new String("This is a String"));
Output: true
```
String object is different from string literal so it will false for the below statement.
```
console.log("This is a String" === new String("This is a String"));
Output: false
```
