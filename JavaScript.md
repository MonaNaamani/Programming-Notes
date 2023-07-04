# JavaScript

## Outline

1. [Introduction](#Introduction)
2.

## Introduction: <a id="Introduction"></a>

The programs in this language are called scripts. They can be written right in a web page’s HTML and run automatically as the page loads. These are called **Internal script**: `<script> </script>`. They can also be in a a separate file, you then link it inside of an HTML’s body, preferably towards the end. **External script** `<script src="javascript.js"></script>`. The old HTML standard, HTML4, required a script to have a type. Usually it was type="text/javascript". It’s not required anymore. 

A single `<script>` tag can’t have both the src attribute and code inside. We must choose either an external `<script src="…">` or a regular `<script>` with code. As a rule, only the simplest scripts are put into HTML. More complex ones reside in separate files. The benefit of a separate file is that the browser will download it and store it in its cache. Other pages that reference the same script will take it from the cache instead of downloading it, so the file is actually downloaded only once. That reduces traffic and makes pages faster.

JavaScript can execute not only in the browser, but also on the server, or actually on any device that has a special program called the JavaScript engine. The browser has an embedded engine sometimes called a “JavaScript virtual machine”. Different engines have different “codenames”. For example:
- V8 – in Chrome, Opera and Edge.
- SpiderMonkey – in Firefox.

The terms above are good to remember because they are used in developer articles on the internet. We’ll use them too. For instance, if “a feature X is supported by V8”, then it probably works in Chrome, Opera and Edge.

For a long time, JavaScript evolved without compatibility issues. New features were added to the language while old functionality didn’t change. That had the benefit of never breaking existing code. But the downside was that any mistake or an imperfect decision made by JavaScript’s creators got stuck in the language forever. This was the case until 2009 when ECMAScript 5 (ES5) appeared. It added new features to the language and modified some of the existing ones. To keep the old code working, most such modifications are off by default. You need to explicitly enable them with a special directive: `"use strict"`. Quite soon we’re going to learn functions (a way to group commands), so let’s note in advance that "use strict" can be put at the beginning of a function. Doing that enables strict mode in that function only. But usually people use it for the whole script. Please make sure that "use strict" is at the top of your scripts, otherwise strict mode may not be enabled.

JavaScript ignores multiple spaces. You can add white space to your script to make it more readable.

JavaScript statements can be grouped together in code blocks, inside curly brackets {...}. Variables declared inside a { } block cannot be accessed from outside the block. 
``` 
{
  let x = 2;
}
// x can NOT be used here
```
## Datatypes

#### 1. String

In JavaScript, there are 3 types of quotes.

- Double quotes: "Hello".
- Single quotes: 'Hello'.
- Backticks: `Hello`.

Double and single quotes are “simple” quotes. There’s practically no difference between them in JavaScript. Backticks are “extended functionality” quotes. They allow us to embed variables and expressions into a string by wrapping them in `${…}`.

#### 2. Number

There are many operations for numbers, e.g. multiplication *, division /, addition +, subtraction -, and so on.

Besides regular numbers, there are so-called “special numeric values” which also belong to this data type: Infinity, -Infinity, and NaN.
- Infinity represents the mathematical Infinity ∞. It is a special value that’s greater than any number.
- NaN represents a computational error. It is a result of an incorrect or an undefined mathematical operation, for instance: `alert( "not a number" / 2 ); // NaN, such division is erroneous`. If there’s a NaN somewhere in a mathematical expression, it propagates to the whole result (there’s only one exception to that: NaN ** 0 is 1).

#### 3. Bigint

In JavaScript, the “number” type cannot safely represent integer values larger than (253-1) (that’s 9007199254740991), or less than -(253-1) for negatives. BigInt type was recently added to the language to represent integers of arbitrary length. A BigInt value is created by appending n to the end of an integer: `const bigInt = 1234567890123456789012345678901234567890n` (the "n" at the end means it's a BigInt). BigInt numbers are rarely needed.

#### 4. Boolean (logical type)

The boolean type has only two values: true and false. This type is commonly used to store yes/no values: true means “yes, correct”, and false means “no, incorrect”. `let nameFieldChecked = true;`

Boolean values also come as a result of comparisons `let isGreater = 4 > 1;`

#### 5. Null

Null is a special value which represents “nothing”, “empty” or “value unknown”. `let age = null;`

#### 6. Undefined

The meaning of undefined is “value is not assigned”. If a variable is declared, but not assigned, then its value is undefined. Technically, it is possible to explicitly assign undefined to a variable. …But we don’t recommend doing that. Normally, one uses null to assign an “empty” or “unknown” value to a variable, while undefined is reserved as a default initial value for unassigned things.

#### 7 Symbols 

#### 8 Objects 

The object data type can contain: an object, an array, a date. 

  - // Object: objects are written with curly braces {}. `const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};` The object (person) in the example above has 4 properties: firstName, lastName, age, and eyeColor.
  - // Array object: `const cars = ["Saab", "Volvo", "BMW"];` arrays are written with square brackets.
  - // Date object: `const date = new Date("2022-03-25");`

## Display

JavaScript can "display" data in different ways:

- Writing into an HTML element, using `innerHTML`: To access an HTML element, JavaScript can use the document.getElementById(id) method. The id attribute defines the HTML element. The innerHTML property defines the HTML content.
- Writing into the HTML output using `document.write()`: for testing purposes, it is convenient to use this method. Using document.write() after an HTML document is loaded, will delete all existing HTML.
- Writing into an alert box, using `alert()`
- Writing into the browser console, `using console.log()`
- You can also call the `window.print()` method in the browser to print the content of the current window

## JavaScript Uses

- Change HTML Content: `document.getElementById("demo").innerHTML = "Hello JavaScript";` this findss an HTML element (with id="demo"), and changes the element content (innerHTML) to "Hello JavaScript".
- Change HTML Attribute Values: For example, JavaScript can change the value of the src (source) attribute of an image. `<button onclick="document.getElementById('myImage').src='pic_bulbon.gif'">Turn on the light</button>`
- Change HTML Styles (CSS): `<button type="button" onclick="document.getElementById('demo').style.fontSize='35px'">Click Me!</button>`
- Hide HTML Elements: Hiding HTML elements can be done by changing the display style. `document.getElementById("demo").style.display = "none";`
- Show HTML Elements: Showing hidden HTML elements can also be done by changing the display style `document.getElementById("demo").style.display = "block";`

## JavaScript Keywords

- `var`	Declares a variable
- `let`	Declares a block variable
- `const`	Declares a block constant
- `if`	Marks a block of statements to be executed on a condition
- `switch`	Marks a block of statements to be executed in different cases
- `for`	Marks a block of statements to be executed in a loop
- `function`	Declares a function
- `return`	Exits a function
- `try`	Implements error handling to a block of statements


## Functions

- `alert` It shows a message and waits for the user to press “OK”. `alert("Hello");`
- `prompt` shows a message asking the user to input text. It returns the text or, if Cancel button or Esc is clicked, null. `result = prompt(title, [default]);` The square brackets around default in the syntax above denote that the parameter is optional, not required. The visitor can type something in the prompt input field and press OK. Then we get that text in the result.
- `confirm` shows a message and waits for the user to press “OK” or “Cancel”. It returns true for OK and false for Cancel/Esc. `result = confirm(question);`















## Variables and Constants

JavaScript Variables can be declared either automatically or using var/let/const. It's a good programming practice to declare all variables at the beginning of a script.

Creating a variable in JavaScript is called "declaring" a variable, and we use the `let` keyword such as `let message;`. After the declaration, the variable has no value (technically it is undefined). To assign a value to the variable, use the equal sign: `message = 'Hello';` or `let message = 'Hello!'`. 

To declare a constant (unchanging) variable, use const: `const myBirthday = '18.04.1982';` Variables declared using const are called “constants”. They cannot be reassigned. An attempt to do so would cause an error. Being a “constant” just means that a variable’s value never changes. But there are constants that are known prior to execution (like a hexadecimal value for red) and there are constants that are calculated in run-time, during the execution, but do not change after their initial assignment. Capital-named constants are only used as aliases for “hard-coded” values. For example `const COLOR_RED = "#F00";`.

Declaring twice triggers an error. A variable should be declared only once.

There are two limitations on variable names in JavaScript:
1. The name must contain only letters, digits, or the symbols $ and _.
2. The first character must not be a digit.

There is a list of reserved words, which cannot be used as variable names because they are used by the language itself. For example: let, class, return, and function are reserved.

## Operators

The numbers (in an arithmetic operation) are called operands. The operation (to be performed between the two operands) is defined by an operator.

### Increment/Decrement

Increment/decrement can only be applied to variables. Trying to use it on a value like 5++ will give an error.The operators ++ and -- can be placed either before or after a variable.

- “postfix form”: when the operator goes after the variable `counter++`.If we’d like to increment a value but use its previous value, we need the postfix form. counter++ returns the "old" value.
- “prefix form”: is when it goes before the variable `++counter`. If we’d like to increase a value and immediately use the result of the operator, we need the prefix form

`++`	Increment: ++ increases a variable by 1
`--`	Decrement: -- decreases a variable by 1

### Assignment Operator

In JavaScript, the equal sign (=) is an **assignment operator**, not an "equal to" operator. The "equal to" operator is written like == in JavaScript.

`+=`	x += y	x = x + y
`-=`	x -= y	x = x - y
`*=`	x *= y	x = x * y
`/=`	x /= y	x = x / y
`%=`	x %= y	x = x % y
`**=`	x **= y	x = x ** y

Both ==  and ===  are used for comparisons and to find the degree of sameness or equality between the things we are comparing, they return true if they find equality and false otherwise. All the **comparison operators** can also be used on strings too. 

`==`	equal to: if the datatypes of the operands we are comparing are different, then the JavaScript Engine automatically converts one of the operands to be the same as the other one in order to make the comparison possible.
`===`	equal value and equal type
`!=`	not equal
`!==`	not equal value or not equal type
`>`	greater than
`<`	less than
`>=`	greater than or equal to
`<=`	less than or equal to
`?`	ternary operator

### Logical Operators

Although they are called “logical”, they can be applied to values of any type, not only boolean. Their result can also be of any type. There are four logical operators in JavaScript:

1. `&&`	logical (AND)
2. `||`	logical (OR)
3. `!`	logical (NOT)
4. `??` logical (Nullish Coalescing)

#### 1. && logical (AND)

#### 2. || logical (OR)

In classical programming, the logical OR is meant to manipulate boolean values only. If any of its arguments are true, it returns true, otherwise it returns false. There are four possible logical combinations for boolean values:

1. alert( true || true );   // true
2. alert( false || true );  // true
3. alert( true || false );  // true
4. alert( false || false ); // false

If an operand is not a boolean, it’s converted to a boolean for the evaluation. For instance, the number 1 is treated as true, the number 0 as false. For example: 
```
let hour = 9;
if (hour < 10 || hour > 18) {
  alert( 'The office is closed.' );}
```

We can pass more conditions:

let hour = 12;
let isWeekend = true;

if (hour < 10 || hour > 18 || isWeekend) {
  alert( 'The office is closed.' ); // it is the weekend}

#### 3. ! logical (NOT)

#### 4. ?? logical (Nullish Coalescing)

### Type Operators

The typeof operator returns the type of the operand. It’s useful when we want to process values of different types differently or just want to do a quick check.

- `typeof`	Returns the type of a variable, Some people prefer `typeof(x)`, although the `typeof x` syntax is much more common.
- `instanceof`	Returns true if an object is an instance of an object type.

The result of typeof null is "object". That’s an officially recognized error in typeof, coming from very early days of JavaScript and kept for compatibility.

### Strings

JavaScript counts positions from zero. First position is 0. Second position is 1.

- `String length`: The length property returns the length of a string
  
- `String slice()`: slice() extracts a part of a string and returns the extracted part in a new string. text.slice(7,13) If you omit the second parameter, the method will slice out the rest of the string. If a parameter is negative, the position is counted from the end of the string text.slice(-12)
  
- `String substring()`: substring() is similar to slice(). The difference is that start and end values less than 0 are treated as 0 in substring().
  
- `String substr()`: substr() is similar to slice(). The difference is that the second parameter specifies the length of the extracted part.If the first parameter is negative, the position counts from the end of the string.
  
- `String replace()`: The replace() method replaces a specified value with another value in a string. let text = "Please visit Microsoft!";let newText = text.replace("Microsoft", "W3Schools"); The replace() method does not change the string it is called on. The replace() method returns a new string. The replace() method replaces only the first match. To replace case insensitive, use a regular expression with an `/i` flag (insensitive) /MICROSOFT/i. To replace all matches, use a regular expression with a `/g` flag (global match)
  
- `String replaceAll()`: 
String toUpperCase()
String toLowerCase()
String concat()
String trim()
String trimStart()
String trimEnd()
String padStart()
String padEnd()
String charAt()
String charCodeAt()
String split()