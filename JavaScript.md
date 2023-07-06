# JavaScript

## Outline

1. [Introduction](#Introduction)
2. [Datatypes](#Datatypes) 
2.

## Introduction <a id="Introduction"></a>

The programs in this language are called scripts. They can be written right in a web page’s HTML and run automatically as the page loads. These are called **Internal script**: `<script> </script>`. They can also be in a a separate file, you then link it inside of an HTML’s body, preferably towards the end. **External script** `<script src="javascript.js"></script>`. The old HTML standard, HTML4, required a script to have a type. Usually it was type="text/javascript". It’s not required anymore. 

A single `<script>` tag can’t have both the src attribute and code inside. We must choose either an external `<script src="…">` or a regular `<script>` with code. As a rule, only the simplest scripts are put into HTML. More complex ones reside in separate files. The benefit of a separate file is that the browser will download it and store it in its cache. Other pages that reference the same script will take it from the cache instead of downloading it, so the file is actually downloaded only once. That reduces traffic and makes pages faster.

JavaScript can execute not only in the browser, but also on the server, or actually on any device that has a special program called the JavaScript engine. The browser has an embedded engine sometimes called a “JavaScript virtual machine”. Different engines have different “codenames”. For example:
- V8 – in Chrome, Opera and Edge.
- SpiderMonkey – in Firefox.

The terms above are good to remember because they are used in developer articles on the internet. We’ll use them too. For instance, if “a feature X is supported by V8”, then it probably works in Chrome, Opera and Edge.

For a long time, JavaScript evolved without compatibility issues. New features were added to the language while old functionality didn’t change. That had the benefit of never breaking existing code. But the downside was that any mistake or an imperfect decision made by JavaScript’s creators got stuck in the language forever. This was the case until 2009 when ECMAScript 5 (ES5) appeared. It added new features to the language and modified some of the existing ones. To keep the old code working, most such modifications are off by default. You need to explicitly enable them with a special directive: `"use strict"`. Quite soon we’re going to learn functions (a way to group commands), so let’s note in advance that "use strict" can be put at the beginning of a function. Doing that enables strict mode in that function only. But usually people use it for the whole script. Please make sure that "use strict" is at the top of your scripts, otherwise strict mode may not be enabled.

JavaScript ignores multiple spaces. You can add white space to your script to make it more readable.

JavaScript statements can be grouped together in code blocks, inside curly brackets {...}. Variables declared inside a { } block cannot be accessed from outside the block. For example:
``` 
{
  let x = 2;
}
// x can NOT be used here
```
## Datatypes <a id="Datatypes"></a>

#### 1. String

In JavaScript, there are 3 types of quotes.

- Double quotes: `"Hello"`.
- Single quotes: `'Hello'`.
-  Backticks: ``` `Hello` ```.

Double and single quotes are “simple” quotes. There’s practically no difference between them in JavaScript. Backticks are “extended functionality” quotes. They allow us to embed variables and expressions into a string by wrapping them in `${…}`.

#### 2. Number

There are many operations for numbers, e.g. multiplication *, division /, addition +, subtraction -, and so on.

Besides regular numbers, there are so-called “special numeric values” which also belong to this data type: Infinity, -Infinity, and NaN.
- Infinity represents the mathematical Infinity ∞. It is a special value that’s greater than any number.
- NaN represents a computational error. It is a result of an incorrect or an undefined mathematical operation, for instance: alert( "not a number" / 2 ); // NaN, such division is erroneous. If there’s a NaN somewhere in a mathematical expression, it propagates to the whole result (there’s only one exception to that: NaN ** 0 is 1).

#### 3. Bigint

In JavaScript, the “number” type cannot safely represent integer values larger than (253-1) (that’s 9007199254740991), or less than -(253-1) for negatives. BigInt type was recently added to the language to represent integers of arbitrary length. A BigInt value is created by appending n to the end of an integer: const bigInt = 1234567890123456789012345678901234567890n (the "n" at the end means it's a BigInt). BigInt numbers are rarely needed.

#### 4. Boolean (logical type)

The boolean type has only two values: true and false. This type is commonly used to store yes/no values: true means “yes, correct”, and false means “no, incorrect”. `let nameFieldChecked = true;`

Boolean values also come as a result of comparisons `let isGreater = 4 > 1;`

#### 5. Null

Null is a special value which represents “nothing”, “empty” or “value unknown”. `let age = null;`

#### 6. Undefined

The meaning of undefined is “value is not assigned”. If a variable is declared, but not assigned, then its value is undefined. Technically, it is possible to explicitly assign undefined to a variable. …But we don’t recommend doing that. Normally, one uses null to assign an “empty” or “unknown” value to a variable, while undefined is reserved as a default initial value for unassigned things.

#### 7. Symbols 

#### 8. Objects 

The object data type can contain: an object, an array, a date. 

  - Object: objects are written with curly braces {}. `const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};` The object (person) in the example above has 4 properties: firstName, lastName, age, and eyeColor.
  - Array object: arrays are written with square brackets `const cars = ["Saab", "Volvo", "BMW"];` 
  - Date object: `const date = new Date("2022-03-25");`

## Functions

- `alert` It shows a message and waits for the user to press “OK”. `alert("Hello");`
- `prompt` shows a message asking the user to input text. It returns the text or, if Cancel button or Esc is clicked, null. `result = prompt(title, [default]);` The square brackets around default in the syntax above denote that the parameter is optional, not required. The visitor can type something in the prompt input field and press OK. Then we get that text in the result.
- `confirm` shows a message and waits for the user to press “OK” or “Cancel”. It returns true for OK and false for Cancel/Esc. `result = confirm(question);`
- `String(value)` is used to convert a value to a string.
- `Number(value)` converts a value to a number, undefined becomes NaN, null becomes	0, true and false become 1 and 0. String whitespaces (includes spaces, tabs \t, newlines \n etc.) from the start and end are removed. If the remaining string is empty, the result is 0. Otherwise, the number is “read” from the string. An error gives NaN. The unary plus or, in other words, the plus operator + applied to a single value, doesn’t do anything to numbers. But if the operand is not a number, the unary plus converts it into a number. It actually does the same thing as Number(...), but is shorter. 
```let x = 1;
alert( +x ); // 1
```
- `Boolean(value)` Values that are intuitively “empty”, like 0, an empty string, null, undefined, and NaN, become false. Other values become true.
- `console.log()`
- `window.print()`
- `document.getElementById(id)`: You can write into an HTML element by using this method, the id attribute defines the HTML element, and the innerHTML property defines the HTML content.
- `document.write()`: for testing purposes, it is convenient to use document.write() after an HTML document is loaded, or it will delete all existing HTML.

## Operators

The numbers (in an arithmetic operation) are called operands. The operation (to be performed between the two operands) is defined by an operator. Operators are things like addition +, multiplication *, subtraction -, and so on. An operator is unary if it has a single operand. An operator is binary if it has two operands. 

### Maths

- Addition +
- Subtraction -
- Multiplication *
- Division /
- Remainder % : despite its appearance, is not related to percents.
- Exponentiation **

The comma operator , is one of the rarest and most unusual operators. The comma operator allows us to evaluate several expressions, dividing them with a comma ,. Each of them is evaluated but only the result of the last one is returned.

### Increment/Decrement

Increment/decrement can only be applied to variables. Trying to use it on a value like 5++ will give an error.The operators ++ and -- can be placed either before or after a variable.

- “postfix form”: when the operator goes after the variable `counter++`. If we’d like to increment a value but use its previous value, we need the postfix form. counter++ returns the "old" value.
- “prefix form”: is when it goes before the variable `++counter`. If we’d like to increase a value and immediately use the result of the operator, we need the prefix form

`++`	Increment: ++ increases a variable by 1
`--`	Decrement: -- decreases a variable by 1

``` 
let a = 1, b = 1;
let c = ++a; 
let d = b++; // a = 2, b = 2, c = 2, d = 1
```
### Assignment Operator

In JavaScript, the equal sign (=) is an **assignment operator**, not an "equal to" operator. The "equal to" operator is written like == in JavaScript.

`+=`	x += y	x = x + y
`-=`	x -= y	x = x - y
`*=`	x *= y	x = x * y
`/=`	x /= y	x = x / y
`%=`	x %= y	x = x % y
`**=`	x **= y	x = x ** y

### Comparison Operators

All comparison operators return a boolean value:
- true – means “yes”, “correct” or “the truth”.
- false – means “no”, “wrong” or “not the truth”.

`!=`	not equal
`!==`	not equal value or not equal type
`>`	greater than
`<`	less than: "apple" < "pineapple" because "a" is smaller than "p"
`>=`	greater than or equal to
`<=`	less than or equal to
`?`	ternary operator

#### `==`	

If the datatypes of the operands we are comparing are different, then the JavaScript Engine automatically converts one of the operands to be the same as the other one in order to make the comparison possible. alert( 0 == false ); // true

There’s a special rule. Null and undefined equal each other (in the sense of ==), but not any other value. The equality check == for undefined and null is defined such that, without any conversions, they equal each other and don’t equal anything else. alert( null == 0 ); // (2) false

For maths and other comparisons < > <= >= null/undefined are converted to numbers: null becomes 0, while undefined becomes NaN. alert( null == undefined ); // true

The value undefined shouldn’t be compared to other values.

#### `===`	

equal value and equal type
```
alert( 0 === false ); // false, because the types are different
```
### Logical Operators

Although they are called “logical”, they can be applied to values of any type, not only boolean. Their result can also be of any type. There are four logical operators in JavaScript:

1. `||`	logical (OR)
2. `&&`	logical (AND)
3. `!`	logical (NOT)
4. `??` logical (Nullish Coalescing)

#### 1. || logical (OR)

In classical programming, the logical OR is meant to manipulate boolean values only. If any of its arguments are true, it returns true, otherwise it returns false. There are four possible logical combinations for boolean values:

1. alert( true || true );   // true
2. alert( false || true );  // true
3. alert( true || false );  // true
4. alert( false || false ); // false

If an operand is not a boolean, it’s converted to a boolean for the evaluation. For instance, the number 1 is treated as true, the number 0 as false. Most of the time, OR || is used in an if statement to test if any of the given conditions is true. For example: 
```
let hour = 12;
let isWeekend = true;

if (hour < 10 || hour > 18 || isWeekend) {
  alert( 'The office is closed.' ); // it is the weekend}
```

Given multiple OR’ed values:

result = value1 || value2 || value3;
The OR || operator does the following:

Evaluates operands from left to right.
For each operand, converts it to boolean. If the result is true, stops and returns the original value of that operand.
If all operands have been evaluated (i.e. all were false), returns the last operand. For instance:

1. Getting the first truthy value from a list of variables or expressions
 
alert( 1 || 0 ); // 1 (1 is truthy)
alert( null || 1 ); // 1 (1 is the first truthy value)
alert( null || 0 || 1 ); // 1 (the first truthy value)
alert( undefined || null || 0 ); // 0 (all falsy, returns the last value)

let firstName = "";
let lastName = "";
let nickName = "SuperCoder";

alert( firstName || lastName || nickName || "Anonymous"); // SuperCoder

2. Short-circuit evaluation

It means that || processes its arguments until the first truthy value is reached, and then the value is returned immediately, without even touching the other argument.

true || alert("not printed");
false || alert("printed");

#### 2. && logical (AND)

In classical programming, AND returns true if both operands are truthy and false otherwise:

alert( true && true );   // true
alert( false && true );  // false
alert( true && false );  // false
alert( false && false ); // false
```
let hour = 12;
let minute = 30;

if (hour == 12 && minute == 30) {
  alert( 'The time is 12:30' );
}
```
The AND && operator evaluates operands from left to right. For each operand, converts it to a boolean. If the result is false, stops and returns the original value of that operand. If all operands have been evaluated (i.e. all were truthy), returns the last operand. The rules above are similar to OR. The difference is that AND returns the first falsy value while OR returns the first truthy one. The precedence of AND && operator is higher than OR ||.

#### 3. ! logical (NOT)

The boolean NOT operator is represented with an exclamation sign !. The syntax is: result = !value;

A double NOT !! is sometimes used for converting a value to boolean type

#### 4. ?? logical (Nullish Coalescing)







### Type Operators

The typeof operator returns the type of the operand. It’s useful when we want to process values of different types differently or just want to do a quick check.

- `typeof`	Returns the type of a variable, Some people prefer `typeof(x)`, although the `typeof x` syntax is much more common.
- `instanceof`	Returns true if an object is an instance of an object type.

The result of typeof null is "object". That’s an officially recognized error in typeof, coming from very early days of JavaScript and kept for compatibility.

## Conditionals

In order to perform different actions based on different conditions we use the if statement and the conditional operator ?, that’s also called a “question mark” operator.

### The “if” statement

We recommend wrapping your code block with curly braces {} every time you use an if statement, even if there is only one statement to execute. Doing so improves readability. The if (…) statement evaluates the expression in its parentheses and converts the result to a boolean. A number 0, an empty string "", null, undefined, and NaN all become false. Because of that they are called “falsy” values. Other values become true, so they are called “truthy”. The if statement may contain an optional else block. It executes when the condition is falsy.

For example:
```
let year = prompt('In which year was the ECMAScript-2015 specification published?', '');

if (year < 2015) {
  alert( 'Too early...' );
} else if (year > 2015) {
  alert( 'Too late' );
} else {
  alert( 'Exactly!' );
}
```
### Conditional operator ‘?’

The operator is represented by a question mark ?. Sometimes it’s called “ternary”, because the operator has three operands. The syntax is: `let result = condition ? value1 : value2;`. The condition is evaluated: if it’s truthy then value1 is returned, otherwise – value2. Example:
```
let age = prompt('age?', 18);

let message = (age < 3) ? 'Hi, baby!' :
  (age < 18) ? 'Hello!' :
  (age < 100) ? 'Greetings!' :
  'What an unusual age!';

alert( message );
```
Here’s how this example looks using if..else:
```









```
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

```





## Variables and Constants

JavaScript Variables can be declared either automatically or using var/let/const. It's a good programming practice to declare all variables at the beginning of a script.

Creating a variable in JavaScript is called "declaring" a variable, and we use the `let` keyword such as `let message;`. After the declaration, the variable has no value (technically it is undefined). To assign a value to the variable, use the equal sign: `message = 'Hello';` or `let message = 'Hello!'`. 

To declare a constant (unchanging) variable, use const: `const myBirthday = '18.04.1982';` Variables declared using const are called “constants”. They cannot be reassigned. An attempt to do so would cause an error. Being a “constant” just means that a variable’s value never changes. But there are constants that are known prior to execution (like a hexadecimal value for red) and there are constants that are calculated in run-time, during the execution, but do not change after their initial assignment. Capital-named constants are only used as aliases for “hard-coded” values. For example `const COLOR_RED = "#F00";`.

Declaring twice triggers an error. A variable should be declared only once.

There are two limitations on variable names in JavaScript:
1. The name must contain only letters, digits, or the symbols $ and _.
2. The first character must not be a digit.

There is a list of reserved words, which cannot be used as variable names because they are used by the language itself. For example: let, class, return, and function are reserved.



### String Methods

A method is a bit of functionality that is built into the language or into specific data types. 

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

