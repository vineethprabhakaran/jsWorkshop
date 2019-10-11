## Strings in Javascript
### 20 String functions:


Lets consider two strings 
```
var stringOne = "Javascript";
var stringTwo = "Javascript is best to learn";
```
* **charAt()** :Returns the character in the specified index of the string.
```
console.log(stringOne.charAt(1));
Output: a
```
* **charCodeAt()** : Returns the unicode of the character at the specified index. 
```
console.log(stringOne.charCodeAt(0));
Output: 74
```

* **concat()** : Returns the concatenated strings.
```
console.log(stringOne.concat(" "+stringTwo));
Output: Javascript Javascript is best to learn
```

* **endsWith()** : Checks if the string ends with the specified string and returns true or false.
```
console.log(stringOne.endsWith("ipt"));
Output: true
```

* **startsWith()** : Checks if the string starts with the specified string and returns true or false.
```
console.log(stringTwo.startsWith("Java"));
Output:
```

* **slice()** : Returns a part of the string. Syntax - slice(startIndex, endIndex + 1).
```
console.log(stringOne.slice(2,6));
Output: vasc
```

* **substring()** : Returns a part of the string. Works similar to the slice method.
```
console.log(stringOne.substring(2,6));
Output: vasc
```

* **substr()** : Returns a part of the string. Syntax - substr(startIndex, number of characters).
```
console.log(stringOne.substr(2,6));
Output: vascri
```

* **fromCharCode()** : Returns the character for the specified unicode.
```
console.log(String.fromCharCode(86));
Output: V
```

* **includes()** : Checks if the string have the specified string and returns true or false.
```
console.log(stringOne.includes("ee"));
Output: false
```

* **indexOf()** : Returns the starting index of the specified string.
```
console.log(stringOne.indexOf("Java"));
Output: 0
```

* **lastIndexOf()** : Returns the starting index of the specified string from the last index.
```
console.log(stringOne.lastIndexOf("a"));
Output: 3
```

* **match(regex expression)** : Returns the matching string.
```
console.log(stringOne.match("s"));
Output: s
```
* **repeat()** : Repeats the string for the specified number of times.
```
console.log(stringOne.repeat(2));
Output: JavascriptJavascript
```

* **search()** : Returns the starting index of the specified string.
```
console.log(stringTwo.search("learn"));
Output: 26
```
* **replace()** : Returns the string with the replaced substring.
```
console.log(stringOne.replace("scr","SCR"));
Output: JavaSCRipt
```

* **toLowerCase()** : Converts the string to lowercase letters.
```
console.log(stringTwo.toLowerCase());
Output: javascript is best to learn
```

* **toUpperCase()** : Converts the string to uppercase letters.
```
console.log("toUpperCase : "+ stringTwo.toUpperCase());
Output: JAVASCRIPT IS BEST TO LEARN
```
* **split()** : Returns a string array with the strings which were split by the specified delimiter. 
```
console.log(stringTwo.split(" "));
Output: Javascript,is,the,best,to,learn
```

* **trim()** : Removes spaces present only at the beginning of the sentance.
```
var spacedString = "      Javascript";
console.log(spacedString.trim());
Output: Javascript
```

