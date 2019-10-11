## Strict mode
* Strict mode in javascript tightens the roles for certain behaviours and these restrictions keeps the code safe and make the javascript engine perform optimization.
* We can enable strict mode by using 'use strict' directive at the beginning of the file or using the directive at the start of the function to enable strict mode for that particular function.
```
use strict; // Enables strict mode for the entire file.

function myFunc(){
	use strict;	 // Enables strict mode for that particular function.
	y = 3.14; // this line will throw an error as this variable needs to be declared.
}

myFunc();
```
* In strict mode deleting a variable is not allowed and it is allowed in normal mode.
* In normal mode the developer will not receive any error feedback when altering non writiable properties but in strict mode it will throw an error.
* In strict mode we will get an error when we write a value in get function.
* In strict mode deleting undeletable properties will throw an error and in normal mode nothing will happen.
* In strict mode function parameter name must be unique.
* Prohibiting the use of 'with' method makes optimization better in javascript.
* Strict mode makes javascript code secure. It will not allow window to be used in a fuction using this keyword when the function is in strict mode. 
