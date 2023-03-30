## 1 What is JS?

- JS (JS) is the world's most popular programming language.
- JS is the programming language of the Web.

## 2 Why Study JS?

JS is one of the 3 languages all web developers must learn:

  1. HTML to define the content of web pages
  2. CSS to specify the layout of web pages
  3. JS to program the behavior of web pages

## 3 Where is JS?

In HTML, JS code is inserted between `<script>` and `</script>` tags.

```html
<script>
document.getElementById("demo").innerHTML = "Hello World!"
</script>
```

## 4 JS Output

JS can "display" data in different ways:

- Writing into an HTML element, using `innerHTML`.
- Writing into the HTML output using `document.write()`.
  >Don't use document.write() after an HTML document is loaded, as it will delete all existing HTML.
- Writing into an alert box, using `window.alert()`.
- Writing into the browser console, using `console.log()`.

## 5 JS Syntax

### JS Values
The JS syntax defines two types of values:

- Fixed values (Literals)
- Variable values (Variables)

#### Literals

- Numbers are written with or without decimals: `10.50`, `1001`.
- Strings are text, written within double or single quotes: `"John Doe"`, `'John Doe'`.

#### Variables

In a programming language, variables are used to store data values.

JS uses the keywords `var`, `let` and `const` to declare variables:

```js
let x = 6
```

### JS Comments
Not all JS statements are "executed".

Code after double slashes `//` or between `/*` and `*/` is treated as a comment.

Comments are ignored, and will not be executed:

```js
let x = 5 // I will be executed
// x = 6  I will NOT be executed
```

### JS Identifiers / Names

Identifiers are JS names.

Identifiers are used to name variables and keywords, and functions.

A JS name must begin with:

- A letter (A-Z or a-z)
- A dollar sign ($)
- Or an underscore (_)

Subsequent characters may be letters, digits, underscores, or dollar signs.

>Numbers are not allowed as the first character in names.
>This way JS can easily distinguish identifiers from numbers.

### JS and camelCase
Historically, programmers have used different ways of joining multiple words into one variable name:

- Hyphens: first-name, last-name, master-card, inter-city.
  >Hyphens are not allowed in JS. They are reserved for subtractions.
- Underscore: first_name, last_name, master_card, inter_city.
- Upper Camel Case (Pascal Case): FirstName, LastName, MasterCard, InterCity.
- Lower Camel Case: firstName, lastName, masterCard, interCity.

JS programmers tend to use camel case that starts with a lowercase letter: *firstName*, *lastName*, *masterCard*, *interCity*.

## 6 JS Variables

There are 4 Ways to Declare a JS Variable:

- Using var
- Using let
- Using const
- Using nothing

### 1. When to use `var`?

Always declare JS variables with `var`, `let`, or `const`.

The `var` keyword is used in all JS code from 1995 to 2015.

The `let` and `const` keywords were added to JS in 2015.

If you want your code to run in older browsers, you must use `var`.

### 2. When to Use `const`?

If you want a general rule: always declare variables with `const`.

If you think the value of the variable can change, use `let`.

### 3. Declaring a Variable

Creating a variable in JS is called "declaring" a variable.

```js
let carName
```

After the declaration, the variable has no value (technically it is undefined).

To assign a value to the variable, use the equal sign:

```js
carName = "Volvo"
```

>It's a good programming practice to declare all variables at the beginning of a script.

### 4. Re-Declaring Variables

If you re-declare a JS variable declared with `var`, it will not lose its value.

The variable `carName` will still have the value "Volvo" after the execution of these statements:

```js
var carName = "Volvo"
var carName
```

You cannot re-declare a variable declared with `let` or `const`.

This will not work:

```js
let carName = "Volvo"
let carName
```

## 7 The `let` keyword

The `let` keyword was introduced in ES6 (2015).

Variables defined with `let`:

- Must be declared before use.
- Cannot be redeclared.
- Have block scope.

### 1. Must be declared before use

Variables defined with `let` must be declared before use.

### 2. Cannot be Redeclared

Variables defined with `let` cannot be redeclared.

```js
let x = "John Doe"
// With let you cannot do this
let x = 0
```

You can not accidentally redeclare a variable declared with `let`, unlike with `var`.

### 3. Block Scope

ES6 introduced two important new JS keywords: `let` and `const`.

These two keywords provide **Block Scope** in JS.

Variables declared inside a { } block cannot be accessed from outside the block:

```js
{
  let x = 2
}
// x can NOT be used here
```

Variables declared with the `var` keyword cannot have Block Scope, so variables declared inside a { } block can be accessed from outside the block.

## 8 The `const` keyword

The `const` keyword was introduced in ES6 (2015).

Variables defined with const:
- Cannot be redeclared.
- Cannot be reassigned.
- Have block scope.

### 1. Constant Objects and Arrays

The keyword `const` is a little misleading.

It does not define a constant value. It defines a constant reference to a value.

Because of this you cannot:

- Reassign a constant value
- Reassign a constant array
- Reassign a constant object

But you can:

- Change the elements of constant array
- Change the properties of constant object

## 9 JS Data Types

JS has 8 Datatypes
- String
- Number
- Bigint
- Boolean
- Undefined
- Null
- Symbol
- Object

The object data type can contain:

- An object
- An array
- A date

## 10 JS Functions

A JS function is a block of code designed to perform a particular task.

The code inside the function will execute when "something" invokes (calls) the function:

- When an event occurs (when a user clicks a button)
- When it is invoked (called) from JS code
- Automatically (self invoked)

## 11 JS Errors

The `try` statement defines a code block to run (to try).

The `catch` statement defines a code block to handle any error.

The `finally` statement defines a code block to run regardless of the result.

The `throw` statement defines a custom error.

### 1. The `throw` Statement
The throw statement allows you to create a custom error.

Technically you can throw an exception (throw an error).

The exception can be a JS `String`, a `Number`, a `Boolean` or an `Object`:

```js
throw "Too big"    // throw a text
throw 500          // throw a number
```

If you use `throw` together with `try` and `catch`, you can control program flow and generate custom error messages.

### 2. JS `try` and `catch`

The `try` statement allows you to define a block of code to be tested for errors while it is being executed.

The `catch` statement allows you to define a block of code to be executed, if an error occurs in the try block.

The JS statements `try` and `catch` come in pairs:

```js
try {
  // Block of code to try
}
catch(err) {
  // Block of code to handle errors
}
```

When an error occurs, JS will normally stop and generate an error message. That means JS will create an Error object.

### 3. The `finally` Statement
The finally statement lets you execute code, after try and catch, regardless of the result:

Syntax
try {
  Block of code to try
}
catch(err) {
  Block of code to handle errors
}
finally {
  Block of code to be executed regardless of the try / catch result
}

#### Example

The example below throws an error if the input value isn't in the range from 0 to 10.

```js
document.getElementById("app").innerHTML = ""
  let myValue = document.getElementById("demo").value
  try {
    if(myValue.trim() == "") throw "is empty"
    if(isNaN(myValue)) throw "is not a number"
    myValue = Number(myValue)
    if(myValue > 10) throw "is too high"
    if(myValue < 0) throw "is too low"
  }
  catch(err) {
    message.innerHTML = "Input " + err
  }
  finally {
    document.getElementById("demo").value = ""
  }
```

### 4. The Error Object

JS has a built in error object that provides error information when an error occurs.

The error object provides two useful properties: name and message.

| Property|	Description
|---|---|
name|	Sets or returns an error name
message|	Sets or returns an error message (a string)

Six different values can be returned by the error name property:

| Error Name|	Description
|---|---|
EvalError|	An error has occurred in the eval() function
RangeError|	A number "out of range" has occurred
ReferenceError|	An illegal reference has occurred
SyntaxError|	A syntax error has occurred
TypeError|	A type error has occurred
URIError|	An error in encodeURI() has occurred

## 11 JS Scope

Scope determines the accessibility (visibility) of variables.

JS has 3 types of scope:

- Block scope
- Function scope
- Global scope

### 1. Block Scope

We talked about Block Scope [here](#3-block-scope).

### 2. Function Scope

JS has **Function Scope**: each function creates a new scope.

Variables defined inside a function are not accessible (visible) from outside the function.

Variables declared with `var`, `let` and `const` are quite similar when declared inside a function: they all have Function Scope.

### 3. Global Scope
Variables declared globally (outside any function) have **Global Scope**.

Global variables can be accessed from anywhere in a JS program.

Variables declared with `var`, `let` and `const` are quite similar when declared outside a block: they all have Global Scope.

#### Automatically Global

If you assign a value to a variable that has not been declared, it will automatically become a global variable.

This code example will declare a global variable carName, even if the value is assigned inside a function.

```js
myFunction()

// code here can use carName

function myFunction() {
  carName = "Volvo"
}
```

#### Global Variables in HTML

With JS, the global scope is the JS environment.

In HTML, the global scope is the window object.

Global variables defined with `var` belong to the window object:

```js
var carName = "Volvo"
// code here can use window.carName
```

Global variables defined with `let` and `const` do not belong to the window object:

```js
let carName = "Volvo"
// code here can not use window.carName
```

>Do NOT create global variables unless you intend to.
>Your global variables (or functions) can overwrite window variables (or functions).
>Any function, including the window object, can overwrite your global variables and functions.

## 12 JS Hoisting

Hoisting is JS's default behavior of moving *variable* (only with `var`) and *function* declarations to the top.

```js
// Variable hoisting
x = 5;
var x;

// This will result in a ReferenceError:
carName1 = "Volvo";
let carName1;

// This is a SyntaxError:
carName2 = "Volvo";
const carName2;

// Function Hoisting
myFunction(5);
function myFunction(x) {
  return x;
}
```

JS in strict mode does not allow variables to be used if they are not declared.

>Hoisting is (to many developers) an unknown or overlooked behavior of JS.
>If a developer doesn't understand hoisting, programs may contain bugs (errors).
>To avoid bugs, always declare all variables at the beginning of every scope.
>Since this is how JS interprets the code, it is always a good rule.

## 13 JS `"use strict"`

The purpose of `"use strict"` is to indicate that the code should be executed in "strict mode".

With strict mode, you can not, for example, use undeclared variables.

All modern browsers support `"use strict"` except Internet Explorer 9 and lower.

Strict mode is declared by adding `"use strict"` to the beginning of a script or a function.

## 14 JS Arrow Function 

Arrow functions allow us to write shorter function syntax:

Without Arrow:
```js
let hello = function(name) {
  return "Hello " + name
}
```

With Arrow:
```js
let hello = (name) => {
  return "Hello " + name
}
```

## 15 JS Classes

JS Classes are templates for JS Objects.

#### Example

```js
class Car {
  constructor(name, year) {
    this.name = name
    this.year = year
  }
    age(now) {
    return now - this.year
  }
}
```

If you do not define a constructor method, JS will add an empty constructor method.

## 16 JS Modules

JS modules allow you to break up your code into separate files. This makes it easier to maintain a code-base.

#### Example

```html
<script type="module">
import message from "./message.js"
</script>
```

### 1. Export

#### Named Exports

In-line individually:

```js
export const name = "Jesse"
export const age = 40
```

All at once at the bottom:

```js
const name = "Jesse"
const age = 40

export {name, age}
```

#### Default Exports

You can only have one default export in a file.

```js
const message = () => {
const name = "Jesse"
const age = 40
return name + ' is ' + age + 'years old.'
}

export default message
```

### 2. Import

#### Import from named exports

```js
import { name, age } from "./person.js"
```

#### Import from default exports

```js
import message from "./message.js"
```

>Modules only work with the HTTP(s) protocol.
>A web-page opened via the file:// protocol cannot use import / export.

## 17 JS Debugging

### 1. The `console.log()` Method

If your browser supports debugging, you can use `console.log()` to display JS values in the debugger window.

### 2. Setting Breakpoints

In the debugger window, you can set breakpoints in the JS code.

At each breakpoint, JS will stop executing, and let you examine JS values.

After examining values, you can resume the execution of code (typically with a play button).

### 3. The `debugger` Keyword
The `debugger` keyword stops the execution of JS, and calls (if available) the debugging function.

This has the same function as setting a breakpoint in the debugger.

```js
let x = 15 * 5
debugger
document.getElementById("demo").innerHTML = x
```

## 18 JS Best Practices

#### Avoid Global Variables

Avoid global variables.

#### Declarations on Top

Put all declarations at the top of each script or function.

```js
// Declare at the beginning
let firstName, lastName

// Use later
firstName = "John"
lastName = "Doe"
```

#### Initialize Variables

It is a good coding practice to initialize variables when you declare them.

```js
// Declare and initiate at the beginning
let firstName = ""
let lastName = ""
```

#### Declare Objects and Arrays with const

Declaring objects with const will prevent any accidental change of type.

```js
let car = {type:"Fiat", model:"500", color:"white"}
car = "Fiat"      // Changes object to string
```

```js
const car = {type:"Fiat", model:"500", color:"white"}
car = "Fiat"      // Not possible
```

#### Don't Use new Object()

Basically, use `""` instead of `new String()`

```js
let x1 = ""             // new primitive string
```

#### Use === Comparison

The `==` comparison operator always converts (to matching types) before comparison.

The `===` operator forces comparison of values and type:

```js
0 == ""        // true
1 == "1"       // true
1 == true      // true

0 === ""       // false
1 === "1"      // false
1 === true     // false
```
