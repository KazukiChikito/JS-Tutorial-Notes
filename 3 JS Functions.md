# JS Functions

#### Example

```js
// Function declaration
function myFunction(a, b) {
  return a * b
}
```

## 1 Self-Invoking Functions

Function expressions can be made "self-invoking": be invoked (started) automatically, without being called.

You cannot self-invoke a function declaration. You have to add parentheses around the function to indicate that it is a function expression:

```js
(function () {
  document.getElementById("app").innerHTML = "Hello! I invoked myself!"
})()
```

The function above is actually an **anonymous self-invoking function** (function without name).

## 2 Arrow Functions

#### Example

```js
// Function expression
var ES5Function = function(x) {
  return x
}

// Arrow Function expression
const ES6Function = (x) => { return x }

// Shorthand. You don't need the function keyword, the return keyword, the parentheses and the curly brackets
const shorthandAF = x => x
```

## 3 Rest Parameter

The rest parameter (...) allows a function to treat an indefinite number of arguments as an array:

```js
function sum(...args) {
  let sum = 0
  for (let arg of args) sum += arg
  return sum
}

let x = sum(4, 9, 16, 25, 29, 100, 66, 77)
```

## 4 The `call()`, `apply()` and `bind()` Function

### 1. `call()`:

With the `call()` method, you can write a method that can be used on different objects.

#### Example

```js
const person = {
  fullName: function() {
    return this.firstName + " " + this.lastName
  }
}
const person1 = {
  firstName:"John",
  lastName: "Doe"
}

// This will return "John Doe":
person.fullName.call(person1)
```

The `call()` method can accept arguments.

#### Example

```js
const person = {
  fullName: function(city, country) {
    return this.firstName + " " + this.lastName + ", " + city + ", " + country
  }
}
const person1 = {
  firstName:"John",
  lastName: "Doe"
}

person.fullName.call(person1, "Oslo", "Norway")
```

### 2. `apply()`:

The `apply()` method is similar to the `call()` method .

The difference is:

- The `call()` method takes arguments separately.
- The `apply()` method takes arguments as an array.

The `apply()` method accepts arguments in an array.

#### Example

```js
const person = {
  fullName: function(city, country) {
    return this.firstName + " " + this.lastName + ", " + city + ", " + country
  }
}
const person1 = {
  firstName:"John",
  lastName: "Doe"
}

person.fullName.apply(person1, ["Oslo", "Norway"])
```

### 3. `bind()`:

With the `bind()` method, an object can borrow a method from another object.

#### Example

```js
const person = {
  firstName:"John",
  lastName: "Doe",
  fullName: function () {
    return this.firstName + " " + this.lastName
  }
}
const person1 = {
  firstName:"John",
  lastName: "Doe"
}

let fullName = person.fullName.bind(person1)
```

#### Preserving `this`

Sometimes the `bind()` method has to be used to prevent losing `this`.

When a function is used as a callback, `this` is lost.

The `bind()` method solves this problem.

#### Example

```js
const person = {
  firstName:"John",
  lastName: "Doe",
  display: function() {
    document.getElementById("demo").innerHTML = this.firstName + " " + this.lastName
  }
}

// This will display undefined, which is undesired
setTimeout(person.display, 3000)

// Using bind() solves the problem
setTimeout(person.display.bind(person), 3000)
```

## 5 Closures

In JS, all functions have access to the scope "above" them.

A closure is a function having access to the parent scope, even after the parent function has closed.

#### Example

```js
const add = (function () {
  let counter = 0
  return function () {
    counter += 1
    return counter
  }
})()

add()
add()
add()
// the counter is now 3
```

#### Example Explained

The variable `add` is assigned to the return value of a self-invoking function.

The self-invoking function only runs once. It sets the counter to zero (0), and returns a function expression. This way `add` becomes a function.

The counter is protected by the scope of the anonymous function, and can only be changed using the `add` function.

This is called a closure. It makes it possible for a function to have "private" variables.
