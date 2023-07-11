# JavaScript

## Outline

1. [Introduction](#Introduction)
2. [Datatypes](#Datatypes)
3. [Functions](#Functions)
4. [Operators](#Operators)
5. [Conditionals](#Conditionals)


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

Double and single quotes are “simple” quotes. There’s practically no difference between them in JavaScript. Backticks are “extended functionality” quotes. They allow us to embed variables and expressions into a string by wrapping them in `${…}`. a template literal is wrapped by backticks ` (this key is usually located on the top of your keyboard, left of the 1 key). Inside the template literal, you’ll see a placeholder, ${...}. The value of ... is inserted into the template literal.

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

## Functions <a id="Functions"></a>

### Built-in functions

- `alert("Hello");` shows a message and waits for the user to press “OK”. 
- `result = prompt(title, [default]);` shows a message asking the user to input text. It returns the text or, if Cancel button or Esc is clicked, null.
- `confirm(question);` shows a message and waits for the user to press “OK” or “Cancel”. It returns true for OK and false for Cancel/Esc.
- `String(value)` is used to convert a value to a string.
- `Number(value)` converts a value to a number, undefined becomes NaN, null becomes	0, true and false become 1 and 0. String whitespaces (includes spaces, tabs \t, newlines \n etc.) from the start and end are removed. If the remaining string is empty, the result is 0. Otherwise, the number is “read” from the string. An error gives NaN. The unary plus or, in other words, the plus operator + does the same thing as Number(...), but is shorter. //alert( +x );
- `Boolean(value)` Values that are intuitively “empty”, like 0, an empty string, null, undefined, and NaN, become false. Other values become true.
- `window.print()`
- `console.log()`: used to debug and test their code in an interactive terminal.
- `document.write()`: inserts text into the document (the webpage in the browser window). It is rather old school and hardly used anymore since it requires embedding in the actual page which is discouraged in this day and age.

### Function Declaration

Just like how a variable declaration binds a value to a variable name, a function declaration binds a function to a name, or an identifier. The function keyword goes first, then goes the name of the function, then a list of parameters between the parentheses (comma-separated, or empty) and finally the code of the function, also named “the function body”, between curly braces.
```
function showMessage() {
  alert( 'Hello everyone!' );
}
```
Our new function can be called by its name: `showMessage();`. The call showMessage() executes the code of the function. We should be aware of the hoisting feature in JavaScript which allows access to function declarations before they’re defined.

A variable declared inside a function is only visible inside that function, but a function can access an outer variable. If a same-named variable is declared inside the function then it shadows the outer one.

Variables declared outside of any function, such as the outer userName in the code above, are called global. Global variables are visible from any function (unless shadowed by locals). It’s a good practice to minimize the use of global variables. Modern code has few or no globals. Most variables reside in their functions. Sometimes though, they can be useful to store project-level data.

If a function is called, but an argument is not provided, then the corresponding value becomes undefined. We can specify the so-called **“default”** (to use if omitted) value for a parameter in the function declaration, using =:
```
function showMessage(from, text = "no text given") {
  alert( from + ": " + text );
}
showMessage("Ann"); // Ann: no text given
```

### Returning a value

The return statement can only be used within function bodies. 

JavaScript allows us to return an “undefined” value. It's not defined. We don't know what the value is, so we can say it's empty. You can do that by writing `return undefined`, `return`, or by removing the statement altogether.

`return` is a “blocking” statement in the scope of the parent function. Which means that it indicates the stopping of the function in which it is. It's important to understand because it means that the code is located after a return statement will never be executed. The code located after a return statement is what we call “dead code”. In fact, the return statement literally means : “this function is done running properly, here is the result you can show to the parent context. No need to read further.”.

```
function getRectArea(width, height) {
  if (width > 0 && height > 0) {
    return width * height;
  }
  return 0;
}

console.log(getRectArea(3, 4));
// Expected output: 12

console.log(getRectArea(-3, 4));
// Expected output: 0
```



#### Writing code after a return

The directive return can be in any place of the function. When the execution reaches it, the function stops, and the value is returned to the calling code. 
```
function checkAge(age) {
  if (age >= 18) {
    return true;
  } else {
    return confirm('Do you have permission from your parents?');
  }
}
```
It is possible to use return without a value. That causes the function to exit immediately. If checkAge(age) returns false, then showMovie won’t proceed to the alert.
```
function showMovie(age) {
  if ( !checkAge(age) ) {
    return;
  }

  alert( "Showing you the movie" ); // (*)
  // ...
}
```
A function with an empty return or without it returns undefined

For a long expression in return, it might be tempting to put it on a separate line. That doesn’t work, because JavaScript assumes a semicolon after return. If we want the returned expression to wrap across multiple lines, we should start it at the same line as return. Or at least put the opening parentheses there as follows:
```
return (
  some + long + expression
  + or +
  whatever * f(a) + f(b)
  )
```

### Naming a function

Functions are actions. So their name is usually a verb. Function starting with:
- "get…" – return a value,
- "show…" – usually show something,
- "calc…" – calculate something,
- "create…" – create something,
- "check…" – check something and return a boolean, etc.

A function should do exactly what is suggested by its name, no more. Two independent actions usually deserve two functions, even if they are usually called together (in that case we can make a 3rd function that calls those two).

## Operators <a id="Operators"></a>

- [Increment/Decrement](#Inc)
- [Assignment](#Assignment)
- [Comparison](#Comparison)
- [Logical](#Logical)
- [Type](#Type)
  
The numbers (in an arithmetic operation) are called operands. The operation (to be performed between the two operands) is defined by an operator. An operator is unary if it has a single operand. An operator is binary if it has two operands. Operators are things like:

- Addition +
- Subtraction -
- Multiplication *
- Division /
- Remainder % : despite its appearance, is not related to percents.
- Exponentiation **
- The comma operator , is one of the rarest and most unusual operators. The comma operator allows us to evaluate several expressions, dividing them with a comma ,. Each of them is evaluated but only the result of the last one is returned.
- The . is another operator called the dot operator.

### Increment/Decrement <a id="Inc"></a>

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
### Assignment Operator <a id="Assignment"></a>

In JavaScript, the equal sign (=) is an **assignment operator**, not an "equal to" operator. The "equal to" operator is written like == in JavaScript.

`+=`	x += y	x = x + y
`-=`	x -= y	x = x - y
`*=`	x *= y	x = x * y
`/=`	x /= y	x = x / y
`%=`	x %= y	x = x % y
`**=`	x **= y	x = x ** y

### Comparison Operators <a id="Comparison"></a>

All comparison operators return a boolean value:
It can be helpful to think of comparison statements as questions. When the answer is “yes”, the statement evaluates to true, and when the answer is “no”, the statement evaluates to false.

`!=`	not equal
`!==`	not equal value or not equal type
`>`	greater than
`<`	less than: "apple" < "pineapple" because "a" is smaller than "p"
`>=`	greater than or equal to
`<=`	less than or equal to
`?`	ternary operator

The list of falsy values includes:
- 0
- Empty strings like "" or ''
- null which represent when there is no value at all
- undefined which represent when a declared variable lacks a value
- NaN, or Not a Number

#### Operator `==`	

If the datatypes of the operands we are comparing are different, then the JavaScript Engine automatically converts one of the operands to be the same as the other one in order to make the comparison possible. alert( 0 == false ); // true

There’s a special rule. Null and undefined equal each other (in the sense of ==), but not any other value. The equality check == for undefined and null is defined such that, without any conversions, they equal each other and don’t equal anything else. alert( null == 0 ); // (2) false

For maths and other comparisons < > <= >= null/undefined are converted to numbers: null becomes 0, while undefined becomes NaN. alert( null == undefined ); // true

The value undefined shouldn’t be compared to other values.

#### Operator `===`	

equal value and equal type
```
alert( 0 === false ); // false, because the types are different
```

#### `?`	ternary operator

We can use a ternary operator to simplify an if...else statement.

isNightTime ? console.log('Turn on the lights!') : console.log('Turn off the lights!');

In the example above:
- The condition, isNightTime, is provided before the ?.
- Two expressions follow the ? and are separated by a colon :.
- If the condition evaluates to true, the first expression executes.
- If the condition evaluates to false, the second expression executes.

### Logical Operators <a id="Logical"></a>

Although they are called “logical”, they can be applied to values of any type, not only boolean. Their result can also be of any type. There are four logical operators in JavaScript:

1. `||`	[logical (OR)](#OR)
2. `&&`	[logical (AND)](#AND)
3. `!`	[logical (NOT)](#NOT)
4. `??` [logical (Nullish Coalescing)](#NULL)

#### 1. || logical (OR) <a id="OR"></a>

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
**Multiple OR’ed values**

result = value1 || value2 || value3;
<font color=green> The OR || operator evaluates operands from left to right. For each operand, converts it to boolean. If the result is true, stops and returns the original value of that operand. If all operands have been evaluated (i.e. all were false), returns the last operand. </font> For instance:

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

The call to alert does not return a value. Or, in other words, it returns undefined.
```
let username = '';
let defaultName = username || 'Stranger';
 
console.log(defaultName); // Prints: Stranger
```
Because || or statements check the left-hand condition first, the variable defaultName will be assigned the actual value of username if it is truthy, and it will be assigned the value of 'Stranger' if username is falsy. This concept is also referred to as short-circuit evaluation.

#### 2. && logical (AND) <a id="AND"></a>

The AND && operator evaluates operands from left to right. For each operand, converts it to a boolean. If the result is false, stops and returns the original value of that operand. If all operands have been evaluated (i.e. all were truthy), returns the last operand. The precedence of AND && operator is higher than OR ||.

<font color=green> AND returns the first falsy value while OR returns the first truthy one. </font>

alert( true && true );   // true
alert( false && true );  // false
alert( true && false );  // false
alert( false && false ); // false
```
let hour = 12;
let minute = 30;

if (hour == 12 && minute == 30) {
  alert( 'The time is 12:30' );}
```
#### 3. ! logical (NOT) <a id="NOT"></a>

The boolean NOT operator is represented with an exclamation sign !. The syntax is: `result = !value`;

A double NOT !! is sometimes used for converting a value to boolean type

#### 4. ?? logical (Nullish Coalescing) <a id="NULL"></a>

As it treats null and undefined similarly, we’ll use a special term here, in this article. For brevity, we’ll say that a value is “defined” when it’s neither null nor undefined.

The result of a ?? b is:
- if a is defined, then a,
- if a isn’t defined, then b.

<font color=green>?? returns the first argument if it’s not null/undefined. Otherwise, the second one.</font> The common use case for ?? is to provide a default value. For example:

let firstName = null;
let lastName = null;
let nickName = "Supercoder";

// shows the first defined value:
alert(firstName ?? lastName ?? nickName ?? "Anonymous"); // Supercoder

The important difference between `??` and `||` is that:
- || returns the first truthy value.
- ?? returns the first defined value.

|| doesn’t distinguish between false, 0, an empty string "" and null/undefined. They are all the same – falsy values. If any of these is the first argument of ||, then we’ll get the second argument as the result. In practice though, we may want to use default value only when the variable is null/undefined.

Due to safety reasons, JavaScript forbids using ?? together with && and || operators, unless the precedence is explicitly specified with parentheses.

### Type Operators <a id="Type"></a>

The typeof operator returns the type of the operand. It’s useful when we want to process values of different types differently or just want to do a quick check.

- `typeof`	Returns the type of a variable, Some people prefer `typeof(x)`, although the `typeof x` syntax is much more common.
- `instanceof`	Returns true if an object is an instance of an object type.

The result of typeof null is "object". That’s an officially recognized error in typeof, coming from very early days of JavaScript and kept for compatibility.

## Conditionals <a id="Conditionals"></a>

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
### The "switch" statement

A switch statement can replace multiple if checks. It gives a more descriptive way to compare a value with multiple variants. The switch has one or more case blocks and an optional default. If the equality is found, switch starts to execute the code starting from the corresponding case, until the nearest break (or until the end of switch). If no case is matched then the default code is executed (if it exists). The values must be of the same type to match.
```
let a = 2 + 2;

switch (a) {
  case 3:
    alert( 'Too small' );
    break;
  case 4:
    alert( 'Exactly!' );
    break;
  case 5:
    alert( 'Too big' );
    break;
  default:
    alert( "I don't know such values" );
}
```
If there is no break then the execution continues with the next case without any checks. The ability to “group” cases is a side effect of how switch/case works without break. Here the execution of case 3 starts from the line (*) and goes through case 5, because there’s no break. Several variants of case which share the same code can be grouped. Such as:
  case 3:
  case 5:
    alert('Wrong!');
    break;

# <font color=red> Unsorted information </font>

## Loops: while and for <font color=red> (Incomplete) </font>

- while
- do..while
- for(..;..;..)

### The “while” loop

## Properties

When you introduce a new piece of data into a JavaScript program, the browser saves it as an instance of the data type. All data types have access to specific properties that are passed down to each instance. For example, every string instance has a property called length that stores the number of characters in that string. You can retrieve property information by appending the string with a period and the property name:

console.log('Hello'.length); // Prints 5

## Methods

Remember that methods are actions we can perform. Data types have access to specific methods that allow us to handle instances of that data type. JavaScript provides a number of string methods.

We call, or use, these methods by appending an instance with:

a period (the dot operator)
the name of the method
opening and closing parentheses
E.g. 'example string'.methodName().

console.log('hello'.toUpperCase()); // Prints 'HELLO'

 the .toUpperCase() method is called on the string instance 'hello'. The result is logged to the console. This method returns a string in all capital letters: 'HELLO'.

console.log('Hey'.startsWith('H')); // Prints true
  On the second line, the .startsWith() method is called on the string instance 'Hey'. This method also accepts the character 'H' as an input, or argument, between the parentheses. Since the string 'Hey' does start with the letter 'H', the method returns the boolean true.

`.random()` method by appending the object name with the dot operator, the name of the method, and opening and closing parentheses. This method returns a random number between 0 (inclusive) and 1 (exclusive).

To generate a random number between 0 and 50, we could multiply this result by 50, like so:

Math.random() * 50;

The example above will likely evaluate to a decimal. To ensure the answer is a whole number, we can take advantage of another useful Math method called Math.floor().

Math.floor() takes a decimal number, and rounds down to the nearest whole number. You can use Math.floor() to round down a random number like this:

Math.floor(Math.random() * 50);

Use the toLowerCase method like below:

'Grace Hopper'.toLowerCase();

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

