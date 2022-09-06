# JavaScript Fundamentals

## 2.3 The Modern Mode, "use strict"

Directive looks like a string: "use strict" or 'use strict'. Located at the top of a script which keeps old code working

``` javascript
"use strict";

// this code works the modern way
...
```


Browsers like FireFox or Chrome can use the console for use strict, should be done in a function style:

``` javascript
(function() {
  'use strict';

  // ...your code here...
})()
```

*Most modern classes and modules have use strict on by default. Just note that if an older code isn't working, this might fix the issue*

## 2.4 Variables

**Variable - "named storage" for data.**
To create a variable, use the **let** keyword

``` javascript
let message;

message = 'Hello'; // store the string 'Hello' in the variable named message

alert(message); // shows the variable content
```

You can also define multiple variables in a multiline style:

``` javascript
let user = 'John',
    age = 24,
    message = 'Hello';
```

You can declare two variables and copy data from one into the other,

``` javascript
let hello = 'Hello World';

let message;

// copy 'Hello World' from hello into message
message = hello

// now to variable hold the same data
console.log(hello); // Hello world
console.log(message); // Hello World 
```

### ⚠️ Declaring twice triggers error

A variable should only be declared once

``` javascript
let message = "this";

// repeated 'let' leads to an error
leg message = "that" // SyntaxError: 'message' has already been declared
```

### Variable naming

Two limitations on variable names:
- The name must contain only letters, digits, or the symbol **$** and **_**.
- The first character must not be a digit.

When the name contains multiple words, camelCase is commonly used. This refers to the first letter being lowercase and the rest of the first letter words being uppercase. For example:

``` javascript
let isExampleOfCamelCase = 2;
let $__$ = 2;

console.log (isExampleOfCamelCase + $__$); // 4
```

### ℹ️ Case Matters
Variables named **apple** and **APPLE** are two different variables.

### Constants 
To declare a constant (unchanging) variable, use const instead of let:

```javascript
const myBirthday = '11.23.1994';

myBirthday = '01.01.2001'; // error, can't reassign constant
```

## Uppercase constants
There is a widespread practice to use constants as aliases for difficult-to-remember values that are known prior to execution. Example:

``` javascript
const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "#00F";
const COLOR_ORANGE = "#FF7F00";

// ...when we need to pick a color
let color = COLOR_ORANGE;
alert(color); // #FF7F00
```

## 2.5 Data types

There are eight basic data types in JavaScript.
- number 
- bigint
- string
- boolean
- null
- undefined
- symbol
- object

### Number

*Number* type represents both integer and floating point numbers.

There are many operations for numbers, ex. multiplication '*', division '/', addition '+', subtraction '-', and so on.

Besides regular numbers, there are so-called "special numeric values" which also belong to this data type: Infinity, -Infinity and NaN.

-  Infinity represents the mathematical Infinity ∞. It is a special value that’s greater than any number.
```javascript 
console.log( 1 / 0 ); // Infinity
// Direct call
console.log( Infinity );
```

NaN represents a computational error.
``` javascript
console.log("not a number" / 2); // NaN, can't divide a string with a number
```
Any further mathematical operation on NaN returns a NaN.

### BigInt
 The “number” type cannot safely represent integer values larger than (2^53-1) (that’s 9007199254740991), or less than -(2^53-1) for negatives.

A **BigInt** value is created by appending n to the end of an integer.
 ``` javascript
const bigInt = 1234567890123456789012345678901234567890n;
 ```

 BigInt is a rarely needed.

 ### String
 A string in JS is surrounded by quotes.

``` javascript
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed strong ${str} `;
```
- Double quotes: "Hello".
- Single quotes: 'Hello'.
- Backticks: `Hello`.