# JavaScript

## Outline

1. [Introduction](#Introduction)
2. [Datatypes](#Datatypes)
3. [Arrays](#Arrays)
4. [Objects](#Objects)
5. [Methods and Properties](#Methods)
6. [Functions](#Functions)
7. [Operators](#Operators)
8. [Conditionals](#Conditionals)
9. [Loops](#Loops)
10. [Errors](#Errors)
11. [Events](#Events)

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

Besides regular numbers, there are so-called “special numeric values” which also belong to this data type: Infinity, -Infinity, and NaN
- NaN represents a computational error. It is a result of an incorrect or an undefined mathematical operation, for instance: alert( "not a number" / 2 ); // NaN, such division is erroneous. If there’s a NaN somewhere in a mathematical expression, it propagates to the whole result (there’s only one exception to that: NaN ** 0 is 1).

#### 3. Bigint

In JavaScript, the “number” type cannot safely represent integer values larger than (253-1) (that’s 9007199254740991), or less than -(253-1) for negatives. A BigInt value is created by appending n to the end of an integer: const bigInt = 1234567890123456789012345678901234567890n (the "n" at the end means it's a BigInt).

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

## Arrays <a id="Arrays"></a>

Each element in an array has a numbered position known as its index. Arrays in JavaScript are zero-indexed, meaning the positions start counting from 0 rather than 1. Therefore, the first item in an array will be at position 0. Variables declared with the const keyword cannot be reassigned. However, elements in an array declared with const remain mutable. Meaning that we can change the contents of a const array, but cannot reassign a new array or a different value.
```
let cities = [ index0, index1, ...]
cities[0] will access the element at index 0 in the array cities.
```
You can also access individual characters in a string using bracket notation and the index. For instance, you can write:
```
const hello = 'Hello World';
console.log(hello[6]); // Output: W
```
### Iterators

Iterators are methods called on arrays to manipulate elements and return values.

- `.length()`: returns the number of items in the array.
- `.push()`: allows us to add items to the end of an array.
- `.join()`: Elements of an array are converted to strings and concatenated together, returning the resulting string.
- `.slice()`: Returns a shallow copy of part of array, while original array is not modified. (from, to).
- `.splice()`: Modifies an array by inserting, deleting, and/or replacing array elements then returns an array of deleted elements.
- `.shift()`: Removes and returns the first element of the array. All subsequent elements will shift down one place.
- `.unshift()`: Adds one or more elements to beginning of array and returns new length.
- `.concat()`: Merges, or concatenates, two or more arrays.
- `.copyWithin()`: Returns a mutated array with part of it copied to another location in the same array, and its length unchanged.
- `.filter()`: Creates a new array with all elements that pass the test from the provided function.
- `.find()`: Returns the first element in the array that satisfies the given function.
- `.findIndex()`: Returns the first index that passes the callback function's test. Returns -1 if no element passes the test.
- `.findLast()`: Returns the last instance of an element in an array that meets the specified condition.
- `.findLastIndex()`: Iterates through the array in reverse order and returns the index that passes the provided testing function.
- `.forEach()`: Loops over the array, passing each item in the array into the callback function provided.
- `.includes()`: Returns true if a given value is included in an array.
- `.indexOf()`: Returns the first index at which an element can be found. Returns -1 if element is not found.
- `.isArray()`: Returns true for arrays, otherwise false.
- `.lastIndexOf()`: Returns the last index at which an element can be found.
- `.length`: Returns the specific number of elements in the array.
- `.map()`: Creates a new array with the results of calling a function for every element in array.
- `.pop()`: Removes the last element of an array, decrements the array length, and returns the value that it removed.
- `.reduce()`: Combines each element of an array, using a specified reducer function, and returns a single value.
- `.reverse()`: Reverses the order of the elements of an array in place and returns the reversed array.
- `.some()`: Runs a conditional through an array and returns a boolean if any value fulfills the conditional.
- `.sort()`: Returns an array with its items sorted in place.
- `.toSorted()`: Takes an array and returns a new array with all the elements sorted in ascending order.
- `.toString()`: Returns a string with each of the array values, separated by commas. Does not mutate the original array.
- `.valueOf()`: Returns the value of all the elements of the original array.
- `.every()`: tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value.

When you pass an array into a function, if the array is mutated inside the function, that change will be maintained outside the function as well.

When an array contains another array it is known as a nested array. 
```
const nestedArr = [[1], [2, 3]];

console.log(nestedArr[1]); // Output: [2, 3]
console.log(nestedArr[1][0]); // Output: 2
```
## Objects <a id="Objects"></a>

An object can be created with figure brackets {…} with an optional list of properties. A property is a “key: value” pair, where key is a string (also called a “property name”), and value can be anything.

An empty object (“empty cabinet”) can be created using one of two syntaxes:
```
let user = new Object(); // "object constructor" syntax
let user = {};  // "object literal" syntax
```
Usually, the figure brackets {...} are used. That declaration is called an object literal.

### Literals and properties

To remove a property, we can use the delete operator:

`delete user.age;`

We can also use multiword property names, but then they must be quoted:
```
let user = {
  name: "John",
  age: 30,
  "likes birds": true  // multiword property name must be quoted
};
```
There are two ways we can access an object’s property:
- dot notation .
- bracket notation [ ]

```
let spaceship = {
  homePlanet: 'Earth',
  color: 'silver'
};
spaceship.homePlanet;

spaceship['homePlanet'];
```
To use bracket notation to access an object’s property, we pass in the property name (key) as a string. With bracket notation you can also use a variable inside the brackets to select the keys of an object.

When the data stored on an object is a function we call that a method. A property is what an object has, while a method is what an object does. With the new method syntax introduced in ES6 we can omit the colon and the function keyword.
```
const alienShip = {
  invade () { 
    console.log('Hello! We have come to dominate your planet. Instead of Earth, it shall be called New Xaculon.')
  }
};
```
We can use square brackets in an object literal, when creating an object. That’s called computed properties. For instance:
```
let fruit = prompt("Which fruit to buy?", "apple");

let bag = {
  [fruit]: 5, // the name of the property is taken from the variable fruit
};

alert( bag.apple ); // 5 if fruit="apple"
```
In real code, we often use existing variables as values for property names. For instance:
```
function makeUser(name, age) {
  return {
    name: name,
    age: age,
    // ...other properties
  };
}
let user = makeUser("John", 30);
alert(user.name); // John
```

In the example above, properties have the same names as variables. The use-case of making a property from a variable is so common, that there’s a special property value shorthand to make it shorter.

Instead of name:name we can just write name, like this:
```
function makeUser(name, age) {
  return {
    name, // same as name: name
    age,  // same as age: age
    // ...
  };
}
```
### Property existence test, “in” operator

The syntax is:
```
"key" in object
```
For instance:
```
let user = { name: "John", age: 30 };

alert( "age" in user ); // true, user.age exists
alert( "bla" in user ); // false, user.bla doesn't exist
```

Please note that on the left side of in there must be a property name. That’s usually a quoted string.

If we omit quotes, that means a variable should contain the actual name to be tested. For instance:
```
let user = { age: 30 };

let key = "age";
alert( key in user ); // true, property "age" exists
```
### The "for..in" loop <a id="forIn"></a>

The for...in statement iterates over all enumerable string properties of an object. If the keys are non-integer, then they are listed in the creation order. If the loop has started, there is a property in the object.

Syntax:
```
for (key in object) {
  // executes the body for each key among object properties
}
```
Also, we could use another variable name here instead of key. For instance, "for (let prop in obj)" is also widely used. Example:
```
let user = {
  name: "John",
  age: 30,
  isAdmin: true
};

for (let key in user) {
  alert( key );  // name, age, isAdmin
  alert( user[key] ); // John, 30, true
}
```


## Methods and Properties <a id="Methods"></a>

JavaScript is an interpreted, object-oriented language that has two main data types: primitives and objects. This data within JavaScript is contained as fields (properties or variables) and code (procedures or methods). Properties and variables are similar in nature, but properties are specifically tied to objects while variables are not.

- Properties: using a method causes something to happen to an object
- Methods: A method is a bit of functionality that is built into the language or into specific data types. Parentheses must be included when a method is used. 

A JavaScript method is a property containing a function definition. In other words, when the data stored on an object is a function we call that a method. To differentiate between properties and methods, we can think of it this way: A property is what an object has, while a method is what an object does.

We call, or use, methods by appending an instance with:

- a period (the dot operator)
- the name of the method
- opening and closing parentheses

You access an object method with the following syntax:
```
objectName.methodName()
```
The methodName property will execute (as a function) when it is invoked with (). If you access the methodName property, without (), it will return the function definition instead of executing an action.

### Properties

- `string.length`: Returns the length of a string.
- 
### Methods

- `string.replace(searchFor, replaceWith)`: Finds every instance of the search for substring and replaces it with the given new substring. 
- `string.toUpperCase()`: Convert all of the characters in a string to capitals. 
- `string.toLowerCase()`: As with toUpperCase. Converts all characters to lower case.
- `string.split(separator, limit)`: Splits the string into an array, split by the provided separator. If an empty string (“”) is provided, it will split each character into a new element in the array.
- `Math.floor(Math.random() * 100) + 1`: Generates a random number between 1 and 100.

### Message Boxes

- alert(message): Display a popup box with the specified message with the OK button.
- confirm(message): Display a popup box with the specified message with OK and Cancel buttons.
- prompt(message, defaultValue): Display a popup box to take the user's input with the OK and Cancel buttons.
```
let userPreference;
if (confirm("Do you want to save changes?") == true) {
    userPreference = "Data saved successfully!";
} else {
    userPreference = "Save Cancelled!";
}
```
### Built-in functions

- `String(value)` is used to convert a value to a string.
- `Number(value)` converts a value to a number, undefined becomes NaN, null becomes	0, true and false become 1 and 0. String whitespaces (includes spaces, tabs \t, newlines \n etc.) from the start and end are removed. If the remaining string is empty, the result is 0. Otherwise, the number is “read” from the string. An error gives NaN. The unary plus or, in other words, the plus operator + does the same thing as Number(...), but is shorter. //alert( +x );
- `Boolean(value)` Values that are intuitively “empty”, like 0, an empty string, null, undefined, and NaN, become false. Other values become true.

## Functions <a id="Functions"></a>

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

#### Function expression vs declaration

A **function expression** is often stored in a variable in order to refer to it. Since the release of ES6, it is common practice to use const as the keyword to declare the variable. To invoke a function expression, write the name of the variable in which the function is stored followed by parentheses enclosing any arguments being passed into the function. `variableName(argument1, argument2)`. Unlike function declarations, function expressions are not hoisted so they cannot be called before they are defined.

A function expression is very similar to, and has almost the same syntax as, a function declaration. The main difference between a function expression and a function declaration is the function name, which can be omitted in function expressions to create anonymous functions. Function expressions in JavaScript are not hoisted, unlike function declarations. You can't use function expressions before you create them.

Function declaration: `function doStuff() {};`
Function expression: `const doStuff = function() {}`
Arrow function: `() => {}`

#### Arrow functions

Functions that take only a single parameter do not need that parameter to be enclosed in parentheses. However, if a function takes zero or multiple parameters, parentheses are required.

A function body composed of a single-line block does not need curly braces. Without the curly braces, whatever that line evaluates will be automatically returned. The contents of the block should immediately follow the arrow => and the return keyword can be removed. This is referred to as implicit return.

So if we have a function:
```
const squareNum = (num) => {
  return num * num;
};
We can refactor the function to:

const squareNum = num => num * num;
```
We wrote a higher-order function higherOrderFunc that accepts a single parameter, param. Inside the body, param gets invoked using parentheses. And finally, a string is returned, telling us the name of the callback function that was passed in.

Below the higher-order function, we have another function aptly named anotherFunc. This function aspires to be called inside the higher-order function.

Lastly, we invoke higherOrderFunc(), passing in anotherFunc as its argument, thus fulfilling its dreams of being called by the higher-order function.
```
higherOrderFunc(() => {
  for (let i = 0; i <= 10; i++){
    console.log(i);
  }
});
```
In this example, we invoked higherOrderFunc() with an anonymous function (a function without a name) that counts to 10. Anonymous functions can be arguments too!

### Functions as Data

JavaScript functions behave like any other data type in the language; we can assign functions to variables, and we can reassign them to new variables. The new function name can be invoked with parentheses as if that was the name we originally gave our function. For example:
```
const busy = announceThatIAmDoingImportantWork;
```
We assign announceThatIAmDoingImportantWork without parentheses as the value to the busy variable because we want to assign the value of the function itself, not the value it returns when invoked.

In JavaScript, functions are first class objects. This means that, like other objects you’ve encountered, JavaScript functions can have properties and methods.Since functions are a type of object, they have properties such as .length and .name, and methods such as .toString(). For example `console.log(function1.name);` indicates the function's name as specified when it was created, or it may be either anonymous or '' (an empty string) for functions created anonymously.

### Functions as Parameters

A higher-order function is a function that either accepts functions as parameters, returns a function, or both! We call functions that get passed in as parameters callback functions. Callback functions get invoked during the execution of the higher-order function.

When we invoke a higher-order function, and pass another function in as an argument, we don’t invoke the argument function. Invoking it would evaluate to passing in the return value of that function call. With callback functions, we pass in the function itself by typing the function name without the parentheses:
```
const higherOrderFunc = param => {
  param();
  return `I just invoked ${param.name} as a callback function!`
}
 
const anotherFunc = () => {
  return 'I\'m being invoked by the higher-order function!';
}
 
higherOrderFunc(anotherFunc);
```
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

All comparison operators return a boolean value. It can be helpful to think of comparison statements as questions. When the answer is “yes”, the statement evaluates to true, and when the answer is “no”, the statement evaluates to false.

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

#### Operator `== and ===`	

If the datatypes of the operands we are comparing are different, then the JavaScript Engine automatically converts one of the operands to be the same as the other one in order to make the comparison possible. alert( 0 == false ); // true.

There’s a special rule. Null and undefined equal each other (in the sense of ==), but not any other value. The equality check == for undefined and null is defined such that, without any conversions, they equal each other and don’t equal anything else. alert( null == 0 ); // (2) false. alert( null == undefined ); // true.

For maths and other comparisons < > <= >= null/undefined are converted to numbers: null becomes 0, while undefined becomes NaN. The value undefined shouldn’t be compared to other values.

=== is equal value and equal type
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

If an operand is not a boolean, it’s converted to a boolean for the evaluation. For instance, the number 1 is treated as true, the number 0 as false. Most of the time, OR || is used in an if statement to test if any of the given conditions is true. 

**Multiple OR’ed values**

result = value1 || value2 || value3;
<font color=green> The OR || operator evaluates operands from left to right. For each operand, converts it to boolean. If the result is true, stops and returns the original value of that operand. If all operands have been evaluated (i.e. all were false), returns the last operand. </font> For instance:

**Getting the first truthy value from a list of variables or expressions**
 
alert( 1 || 0 ); // 1 (1 is truthy)
alert( null || 1 ); // 1 (1 is the first truthy value)
alert( null || 0 || 1 ); // 1 (the first truthy value)
alert( undefined || null || 0 ); // 0 (all falsy, returns the last value)

Example:
```
let firstName = "";
let lastName = "";
let nickName = "SuperCoder";

alert( firstName || lastName || nickName || "Anonymous"); // SuperCoder
```
#### 2. && logical (AND) <a id="AND"></a>

The AND && operator evaluates operands from left to right. For each operand, converts it to a boolean. If the result is false, stops and returns the original value of that operand. If all operands have been evaluated (i.e. all were truthy), returns the last operand. The precedence of AND && operator is higher than OR ||.

<font color=green> AND returns the first falsy value while OR returns the first truthy one. </font>

alert( true && true );   // true
alert( false && true );  // false
alert( true && false );  // false
alert( false && false ); // false

#### 3. ! logical (NOT) <a id="NOT"></a>

The boolean NOT operator is represented with an exclamation sign !. The syntax is: `result = !value`; A double NOT !! is sometimes used for converting a value to boolean type.

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

### The “if” statement

The if (…) statement evaluates the expression in its parentheses and converts the result to a boolean. A number 0, an empty string "", null, undefined, and NaN all become false. Because of that they are called “falsy” values. Other values become true, so they are called “truthy”. The if statement may contain an optional else block. It executes when the condition is falsy.

### Conditional operator ‘?’

The operator is represented by a question mark ?. Sometimes it’s called “ternary”, because the operator has three operands. The syntax is: `let result = condition ? value1 : value2;`. The condition is evaluated: if it’s truthy then value1 is returned, otherwise – value2. Example:
```
let age = prompt('age?', 18);

let message = (age < 3) ? 'Hi, baby!' :
  (age < 18) ? 'Hello!' :
  (age < 100) ? 'Greetings!' :
  'What an unusual age!';
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
  case 6:
    alert( 'Too big' );
    break;
  default:
    alert( "I don't know such values" );
}
```
If there is no break then the execution continues with the next case without any checks. 

## Loops <a id="Loops"></a> 

You’ll hear the generic term iterate when referring to loops; iterate simply means “to repeat”.

- [for](#for)
- [for…of](#forOf)
- [for…in](#forIn)
- [while](#while)
- [do-while](#doWhile)

Iteration methods: 

- [map()](#map)
- [filter()](#filter)
- [forEach()](#forEach)
- [findIndex()](#findIndex)
- [reduce()](#reduce)

### `for` <a id="for"></a>

The loop below runs alert(i) for i from 0 up to (but not including) 3:
```
for (let i = 0; i < 3; i++) { // shows 0, then 1, then 2
  alert(i);
}
```
Here, the “counter” variable i is declared right in the loop. This is called an “inline” variable declaration. Such variables are visible only inside the loop. We can also use an existing variable.

- begin: `let i = 0`	Executes once upon entering the loop.
- a stopping condition: `i < 3`	Checked before every loop iteration. If false, the loop stops. <font color=red> If you omit it, you must provide a break inside the loop. Otherwise the loop will never end. This will crash your browser.</font>
- body: `alert(i)`	Runs again and again while the condition is truthy.
- step: `i++`	Executes after the body on each iteration.

The for loop increases the readability & reduces the chances of error.

Quick heads-up, using const in for-loop will give you an error. Reason why is because it re-declares the value during each execution hence i is modified by i++.

#### Looping in Reverse

To run a backward for loop, we must:

1. Set the iterator variable to the highest desired value in the initialization expression.
2. Set the stopping condition for when the iterator variable is less than the desired amount.
3. The iterator should decrease in intervals after each iteration.

#### Looping through Arrays

When we use i to iterate through arrays we can think of it as being short-hand for the word index. To loop through each element in an array, a for loop should use the array’s .length property in its condition.
```
const animals = ['Grizzly Bear', 'Sloth', 'Sea Lion'];
for (let i = 0; i < animals.length; i++){
  console.log(animals[i]);
}
```
#### Nested Loops

One use for a nested for loop is to compare the elements in two arrays.
```
const myArray = [6, 19, 20];
const yourArray = [19, 81, 2];
for (let i = 0; i < myArray.length; i++) {
  for (let j = 0; j < yourArray.length; j++) {
    if (myArray[i] === yourArray[j]) {
      console.log('Both arrays have the number: ' + yourArray[j]);
    }
  }
}
```
#### Breaking the loop

Normally, a loop exits when its condition becomes falsy. But we can force the exit at any time using the special break directive. For example, the loop below asks the user for a series of numbers, “breaking” when no number is entered:
```
let sum = 0;

while (true) {

  let value = +prompt("Enter a number", '');

  if (!value) break; // (*)

  sum += value;

}
alert( 'Sum: ' + sum );
```
#### Continue to the next iteration

The continue directive is a “lighter version” of break. It doesn’t stop the whole loop. Instead, it stops the current iteration and forces the loop to start a new one (if the condition allows).

We can use it if we’re done with the current iteration and would like to move on to the next one.

The loop below uses continue to output only odd values:
```
for (let i = 0; i < 10; i++) {

  // if true, skip the remaining part of the body
  if (i % 2 == 0) continue;

  alert(i); // 1, then 3, 5, 7, 9
}
```
For even values of i, the continue directive stops executing the body and passes control to the next iteration of for (with the next number). So the alert is only called for odd values.

We can use `continue` with the `if condition` as follows:
```
if (i > 5) {
  alert(i);
} else {
  continue;
}
```
Please note that syntax constructs that are not expressions cannot be used with the ternary operator ?. In particular, directives such as break/continue aren’t allowed there.

### `for...of` <a id="forOf"></a>

Syntax
```
for (variable of iterable)
  statement
```
For example: Iterating over a array
```
const iterable = [10, 20, 30];

for (let value of iterable) {
  value += 1;
  console.log(value);
}
// 11
// 21
// 31
  ```
Iterating over a string
```
const iterable = "boo";

for (const value of iterable) {
  console.log(value);
}
// "b"
// "o"
// "o"
```
### `while` <a id="while"></a>

The syntax of a while loop is ideal when we don’t know in advance how many times the loop should run. In situations when we want a loop to execute an undetermined number of times, while loops are the best choice. The while loop syntax is the following:
```
while (condition) {
  // code
  // so-called "loop body"
}
```
While the condition is truthy, the code from the loop body is executed.
```
let i = 0;
while (i < 3) { // shows 0, then 1, then 2
  alert( i );
  i++;
}
```
A single execution of the loop body is called an iteration. The loop in the example above makes three iterations. If i++ was missing from the example above, the loop would repeat (in theory) forever.

Any expression or variable can be a loop condition, not just comparisons: the condition is evaluated and converted to a boolean by while.

For instance, a shorter way to write while (i != 0) is while (i):
```
let i = 3;
while (i) { // when i becomes 0, the condition becomes falsy, and the loop stops
  alert( i );
  i--;
}
```

### `do-while` <a id="doWhile"></a>

This loop will execute the code block once, before checking if the condition is true, then it will repeat the loop as long as the condition is true. This form of syntax should only be used when you want the body of the loop to execute at least once regardless of the condition being truthy. Usually, the other form is preferred: while(…) {…}.

The condition check can be moved below the loop body using the do..while syntax:

Syntax
```
do {
  // loop body
} while (condition);
```
The loop will first execute the body, then check the condition, and, while it’s truthy, execute it again and again. Example:
```
do {
  text += "The number is " + i;
  i++;
}
while (i < 10);
```
<font color=red> Do not forget to increase the variable used in the condition, otherwise the loop will never end!</font>

### map() <a id="map"></a>

When .map() is called on an array, it takes an argument of a callback function and returns a new array. For example:
```
function toUpper(string) {
  return string.toUpperCase();
}

const cats = ["Leopard", "Serval", "Jaguar", "Tiger", "Caracal", "Lion"];

const upperCats = cats.map(toUpper);

console.log(upperCats);
```
Example 2:
```
const numbers = [1, 2, 3, 4, 5]; 
 
const bigNumbers = numbers.map(number => {
  return number * 10;
});
```
### filter() <a id="filter"></a>

You can use filter() to test each item in a collection, and create a new collection containing only items that match:
```
function lCat(cat) {
  return cat.startsWith("L");
}

const cats = ["Leopard", "Serval", "Jaguar", "Tiger", "Caracal", "Lion"];

const filtered = cats.filter(lCat);

console.log(filtered);
// [ "Leopard", "Lion" ]
```
Using function expressions we could rewrite the example above to be much more compact:
```
const cats = ["Leopard", "Serval", "Jaguar", "Tiger", "Caracal", "Lion"];

const filtered = cats.filter((cat) => cat.startsWith("L"));
console.log(filtered);
// [ "Leopard", "Lion" ]
```
### forEach() <a id="forEach"></a>

The forEach() method executes a provided function once for each array element.Unlike map(), forEach() always returns undefined and is not chainable. The typical use case is to execute side effects at the end of a chain.forEach() does not mutate the array on which it is called, but the function provided as callbackFn can.
```
const groceries = ['Brown sugar', 'Salt']
groceries.forEach(function(groceryItem) {console.log(' - ' + groceryItem);
});

- Brown sugar
- Salt
```
- groceries.forEach() calls the forEach method on the groceries array.
- .forEach() takes an argument of callback function. Remember, a callback function is a function passed as an argument into another function.
- .forEach() loops through the array and executes the callback function for each element. During each execution, the current element is passed as an argument to the callback function.
- The return value for .forEach() will always be undefined.

Another way to pass a callback for .forEach() is to use arrow function syntax.

groceries.forEach(groceryItem => console.log(groceryItem));

### reduce() <a id="reduce"></a>

The .reduce() method returns a single value after iterating through the elements of an array, thereby reducing the array.

- numbers.reduce() calls the .reduce() method on the numbers array and takes in a callback function as argument.
- The callback function has two parameters, accumulator and currentValue. The value of accumulator starts off as the value of the first element in the array and the currentValue starts as the second element. To see the value of accumulator and currentValue change, review the chart above.
- As .reduce() iterates through the array, the return value of the callback function becomes the accumulator value for the next iteration, currentValue takes on the value of the current element in the looping process.

The .reduce() method can also take an optional second parameter to set an initial value for accumulator (remember, the first argument is the callback function!). For instance:
```
const numbers = [1, 2, 4, 10];
 
const summedNums = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue
}, 100)  // <- Second argument for .reduce()
 
console.log(summedNums); // Output: 117
```
## Errors <a id="Errors"></a>

**Syntax Error**: occurs when the code you are trying to run is not written correctly.
   
**ReferenceError**: these arise because whatever variable you are trying to reference does not exist (within the current scope) - or it has been spelled incorrectly.
   
**Type Error**: A good note to keep in mind when faced with a TypeError is to consider the data type you are trying to run a method or operation against. You’ll likely find that it is not what you think, or the operation or method is not compatible with that type. Per MDN, a TypeError may be thrown when:
- an operand or argument passed to a function is incompatible with the type expected by that operator or function;
- or when attempting to modify a value that cannot be changed;
- or when attempting to use a value in an inappropriate way.

## Events <a id="Events"></a>

Events are actions that occur on your webpage such as mouse-clicks or keypresses, and using JavaScript we can make our webpage listen and react to these events. There are three primary ways to go about this: 
1. Method 1: Specify function attributes directly on your HTML elements.
2. Method 2: Set properties of form on eventType on the DOM nodes in your JavaScript.
3. Method 3: Attach event listeners to the DOM nodes in your JavaScript. 

### Method 1

`<button onclick="alert('Hello World')">Click Me</button>`

This solution is less than ideal because we’re cluttering our HTML with JavaScript. Also, we can only set one “onclick” property per DOM element, so we’re unable to run multiple separate functions in response to a click event using this method.

### Method 2
```
<!-- the HTML file -->
<button id="btn">Click Me</button>

<!-- the JavaScript file -->
const btn = document.querySelector('#btn');
btn.onclick = () => alert("Hello World");
```
This is a little better. We’ve moved the JS out of the HTML and into a JS file, but we still have the problem that a DOM element can only have 1 “onclick” property.

### Method 3

```
<!-- the HTML file -->
<button id="btn">Click Me Too</button>

<!-- the JavaScript file -->
const btn = document.querySelector('#btn');
btn.addEventListener('click', () => {
  alert("Hello World");
});
```
Using named functions can clean up your code considerably, and is a really good idea if the function is something that you are going to want to do in multiple places.

With all three methods we can access more information about the event by passing a parameter to the function that we are calling. Try this out on your own machine:

```
btn.addEventListener('click', function (e) {
  console.log(e);
});
```
The e in that function is an object that references the event itself. Within that object you have access to many useful properties and methods (functions that live inside an object) such as which mouse button or key was pressed, or information about the event’s target - the DOM node that was clicked. For example:
```
btn.addEventListener('click', function (e) {
  console.log(e.target);
});


btn.addEventListener('click', function (e) {
  e.target.style.background = 'blue';
});
```
#### Attaching listeners to groups of nodes
```
<div id="container">
    <button id="1">Click Me</button>
    <button id="2">Click Me</button>
    <button id="3">Click Me</button>
</div>
// buttons is a node list. It looks and acts much like an array.
const buttons = document.querySelectorAll('button');

// we use the .forEach method to iterate through each button
buttons.forEach((button) => {

  // and for each one we add a 'click' listener
  button.addEventListener('click', () => {
    alert(button.id);
  });
});
```
In our examples so far we have been using the ‘click’ event exclusively, but there are many more available to you. Some useful events include:
- click
- dblclick
- keydown
- keyup

## React - JSX Introduction (UNSORTED)

### Event Listeners in JSX

An event listener attribute’s name should be something like onClick or onMouseOver: the word on plus the type of event that you’re listening for. An event listener attribute’s value should be a function. 

Note that in HTML, event listener names are written in all lowercase, such as onclick or onmouseover. In JSX, event listener names are written in camelCase, such as onClick or onMouseOver.

Here’s a rule that you need to know: you can not inject an if statement into a JSX expression.

### JSX Conditionals: &&

&& works best for conditionals that will sometimes do an action but other times do nothing at all.

Here’s an example:
```
const tasty = (
  <ul>
    <li>Applesauce</li>
    { !baby && <li>Pizza</li> }
    { age > 15 && <li>Brussels Sprouts</li> }
    { age > 20 && <li>Oysters</li> }
    { age > 25 && <li>Grappa</li> }
  </ul>
);
```
If the expression on the left of the && evaluates as true, then the JSX on the right of the && will be rendered. If the first expression is false, however, then the JSX to the right of the && will be ignored and not rendered.

### .map in JSX

If you want to create a list of JSX elements, then using .map() is often the most efficient way. 
```
const strings = ['Home', 'Shop', 'About Me'];
 
const listItems = strings.map(string => <li>{string}</li>);
 
<ul>{listItems}</ul>
```

### Keys

A key is a JSX attribute. The attribute’s name is key. The attribute’s value should be something unique, similar to an id attribute.

Not all lists need to have keys. A list needs keys if either of the following is true:

The list items have memory from one render to the next. For instance, when a to-do list renders, each item must “remember” whether it was checked off. The items shouldn’t get amnesia when they render.
A list’s order might be shuffled. For instance, a list of search results might be shuffled from one render to the next.
If neither of these conditions is true, then you don’t have to worry about keys. If you aren’t sure, then it never hurts to use them!
```
const people = ['Rowe', 'Prevost', 'Gare'];

const peopleList = people.map((person, i) =>
  <li key={'person_' + i}>{person}</li>
);
```
### React without JSX

You can write React code without using JSX at all!

The majority of React programmers do use JSX, but you should understand that it is possible to write React code without it.

The following JSX expression:

const h1 = <h1>Hello world</h1>;
 
can be rewritten without JSX, like this:

const h1 = React.createElement(
  "h1",
  null,
  "Hello world"
);
 
When a JSX element is compiled, the compiler transforms the JSX element into the method that you see above: React.createElement(). Every JSX element is secretly a call to React.createElement().

## React Components
import React from 'react';
import ReactDOM from 'react-dom/client';

Import React
The first React component we created in the last exercise started with importing react. The line that did this is:

`import React from 'react';`
 
This creates an object named React, which contains methods necessary to use the React library. React is imported from the 'react' package, which should be installed in your project as a dependency. With the object, we can start utilizing features of the react library!

In a React application, the App.js file typically is the top level of your application, and index.js is the entry point.

import ReactDOM from 'react-dom/client';  

Another import we need in addition to React is ReactDOM:

import ReactDOM from 'react-dom/client';
 
The methods imported from 'react-dom' interact with the DOM.

The methods imported from 'react' do not deal with the DOM at all. They don’t engage directly with anything that isn’t part of React.

To clarify: the DOM is used in React applications, but it isn’t part of React. After all, the DOM is also used in countless non-React applications. Methods imported from 'react' are only for pure React purposes, such as creating components or writing JSX elements.

Although we imported React in both App.js and index.js in the previous exercise, we will only import ReactDOM in index.js.

ReactDOM deals with DOM-specific methods that should be used in index.js, which is the entry point of our application.

we can use JavaScript functions to define a new React component. This is called a function component.In the past, React components were defined using Javascript classes. But since the introduction of Hooks (something we’ll discuss later), function components have become the standard in modern React applications.

Function component names must start with capitalization and are conventionally created with PascalCase! Due to how JSX tags are compiled, capitalization indicates that it is a React component rather than an HTML tag.This is a React-specific nuance! If you are creating a component, be sure to name it starting with a capital letter so it interprets it as a React component. If it begins with a lowercase letter, React will begin looking for a built-in component such as div and input instead and fail.

when we define functional components, we must return a JSX element.

React application typically has two core files: App.js and index.js. App.js file is the top level of your application, and index.js is the entry point.

So far, we’ve defined the component inside of App.js, but because index.js is the entry point, we have to export it to index.js to render.

To export them, we can prefix it with the export declaration and specify if it is a default or named export. In this case, we’ll stick with default. 

export : https://developer.mozilla.org/en-US/docs/web/javascript/reference/statements/export

After the function component definition, in App.js, we can default export our component like so:

export default MyComponent;
 
We can head into our index.js file to import our component from './App':

import MyComponent from './App';

Now that we have a defined function component, we can start using it.

We can use it with an HTML-like syntax that resembles a self-closing tag:

<MyComponent />
 
If you need to nest other components in between, you may also use an opening and corresponding closing tag structure:

<MyComponent>
  <OtherComponent />
</MyComponent>
 
 However, to render our component to the browser, we must rely on the .createRoot() and .render() methods from the react-dom library. This should be done in our entry point, index.js.

First, we call the createRoot method to create a React root container for displaying content. React applications typically have a single root DOM node, and everything inside it is managed by React DOM.

In other words, we give createRoot a DOM element to render in, and React will take over managing the DOM inside it.

Here’s an example:

ReactDOM.createRoot(document.getElementById('app'));

Great! Let’s break it down a bit further:

document.getElementById('app') returns a DOM element from index.html.
.createRoot() receives the DOM element as the first argument and creates a root for it.
.createRoot() returns a reference to the root container on which you can call methods like .render().
After the root is created, all that’s left to do is call the .render() method on the returned root and display the React component like so:

ReactDOM.createRoot(document.getElementById('app')).render(<MyComponent />);
 
From here, React will display <MyComponent /> in the root and make it appear on the screen.

In an application fully built with React, you will only need to do this once. Once this is set up, React will manage the DOM of your application, and any updates to the UI is taken care of efficiently. Adding more components should take place in your top-level App.js file.

## DOM - Document Object Model

The DOM is a tree-like representation of the contents of a webpage - a tree of “nodes” with different relationships depending on how they’re arranged in the HTML document.

### Targeting nodes with selectors

When working with the DOM, you use “selectors” to target the nodes you want to work with:
```
<div id="container">
  <div class="display"></div>
  <div class="controls"></div>
</div>
```
- div.display
- .display
- #container > .display
- div#container > div.display

You can also use relational selectors (i.e. firstElementChild or lastElementChild etc.) with special properties owned by the nodes.
- container.firstElementChild: selects the first child of #container => .display
- controls.previousElementSibling: selects the prior sibling => .display

### DOM methods

1. Query selectors: helps us target nodes
2. Element creation
3. Append elements
4. Remove elements
5. Altering elements
6. Adding inline style
7. Editing attributes

#### Query selectors

`element.querySelector(selector)` returns a reference to the first match of selector.

`element.querySelectorAll(selectors)` returns a “nodelist” containing references to all of the matches of the selectors. It’s important to note that when using querySelectorAll, the return value is not an array. It looks like an array, and it somewhat acts like an array, but it’s really a “nodelist”. The big distinction is that several array methods are missing from nodelists. One solution, if problems arise, is to convert the nodelist into an array. You can do this with Array.from() or the spread operator.

#### Element creation

`document.createElement(tagName, [options])` creates a new element of tag type tagName. [options] in this case means you can add some optional parameters to the function.This function does NOT put your new element into the DOM - it simply creates it in memory. This is so that you can manipulate the element (by adding styles, classes, ids, text, etc.) before placing it on the page. 

#### Append elements

`parentNode.appendChild(childNode)` appends childNode as the last child of parentNode.

`parentNode.insertBefore(newNode, referenceNode)` inserts newNode into parentNode before referenceNode.

#### Remove elements

`parentNode.removeChild(child)` removes child from parentNode on the DOM and returns a reference to child.

#### Altering elements
When you have a reference to an element, you can use that reference to alter the element’s own properties. This allows you to do many useful alterations, like adding/removing and altering attributes, changing classes, adding inline style information and more.
```
const div = document.createElement('div');                     
// creates a new div referenced in the variable 'div'
```
#### Adding inline style
```
div.style.color = 'blue';                                      
// adds the indicated style rule

div.style.cssText = 'color: blue; background: white;';          
// adds several style rules

div.setAttribute('style', 'color: blue; background: white;');    
// adds several style rules

Note that if you’re accessing a kebab-cased CSS rule from JS, you’ll either need to use camelCase or you’ll need to use bracket notation instead of dash notation.
```
#### Editing attributes
```
div.setAttribute('id', 'theDiv');                              
// if id exists, update it to 'theDiv', else create an id
// with value "theDiv"

div.getAttribute('id');                                        
// returns value of specified attribute, in this case
// "theDiv"

div.removeAttribute('id');                                     
// removes specified attribute

```
#### Working with classes
It is often standard (and cleaner) to toggle a CSS style rather than adding and removing inline CSS.
```
div.classList.add('new');                                      
// adds class "new" to your new div

div.classList.remove('new');                                   
// removes "new" class from div

div.classList.toggle('active');                                
// if div doesn't have class "active" then add it, or if
// it does, then remove it
```
#### Adding text content
```
div.textContent = 'Hello World!'                               
// creates a text node containing "Hello World!" and
// inserts it in div
```
#### Adding HTML content
```
div.innerHTML = '<span>Hello World!</span>';                   
// renders the HTML inside div
*Note that textContent is preferable for adding text, and innerHTML should be used sparingly as it can create security risks if misused.
```

You can link the JavaScript file in the <head> of your HTML document. Use the <script> tag with the src attribute containing the path to the JS file, and include the defer keyword to load the file after the HTML is parsed, as such:
```
<head>
  <script src="js-file.js" defer></script>
</head>
```





