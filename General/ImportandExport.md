## Import and  Export

* Import and export are used to breakdown content into different files or modules.

###  NAMED EXPORTS

```
//------ lib.js ------
export const sqrt = Math.sqrt;
export function square(x) {
    return x * x;
}
export function diag(x, y) {
    return sqrt(square(x) + square(y));
}
```
### IMPORT PART OF A MODULE

* In the below code only the square and diag are imported from the lib.js file.
```
//------ main.js ------
import { square, diag } from 'lib';
console.log(square(11)); 
console.log(diag(4, 3)); 

```
### IMPORTING COMPLETE MODULE
* Star symbol is used to import the all the contents of the lib.js file.
```
//------ main.js ------
import * as lib from 'lib';
console.log(lib.square(11));
console.log(lib.diag(4, 3)); 
```
### IMPORTING WITH MORE CONVENIENT ALIAS

* When the imported property name is big we can use a different alias name.
```
import {reallyReallyLongModuleMemberName as shortName}
  from 'my-module';
```
### SINGLE DEFAULT EXPORT
* Usually this is used when only one values need to be exported from a file.
* It is also used to create a fallback values for a file or a module.
```
//------ myFunc.js ------
export default function () { ··· } // no semicolon!

//------ main1.js ------
import myFunc from 'myFunc'; // no curly braces used like in other imports.
myFunc();
```
