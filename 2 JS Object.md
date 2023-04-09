# JS Object

## 1 Accessors

Accessors are basically getters and setters.

#### Example

```js
// Create an object:
const person = {
  firstName: "John",
  lastName: "Doe",
  language: "en",
  get getLang() {
    return this.language
  }
  set setLang(lang) {
    this.language = lang
  }
}

// Set an object property using a setter:
person.setLang = "en"

// Display data from the object using a getter:
document.getElementById("demo").innerHTML = person.getLang
```
### 1. Function or Getter?

#### Example

```js
const person = {
  firstName: "John",
  lastName: "Doe",
  fullName: function() {
    return this.firstName + " " + this.lastName
  },
  get getFullName() {
    return this.firstName + " " + this.lastName
  }
}

// Display the function from the object using a method:
document.getElementById("demo1").innerHTML = person.fullName

// Display data from the object using a method:
document.getElementById("demo1").innerHTML = person.fullName()

// Display data from the object using a getter:
document.getElementById("demo").innerHTML = person.getFullName
```

Functions access `fullName` as a function: `person.fullName()`.

Getters access `fName` as a property: `person.fName`.

Getters provide a simpler syntax and allow equal syntax for properties and methods.

## 2 Constructors

#### Example

```js
//  This is an object constructor function
function Person(first, last, age, eye) {
  this.firstName = first
  this.lastName = last
  this.age = age
  this.eyeColor = eye
}

// Creating new Person objects
const myFather = new Person("John", "Doe", 50, "blue")
const myMother = new Person("Sally", "Rally", 48, "green")
```

### 1. Adding to an Object

####  Properties

Adding a new property to an existing object is easy:

```js
myFather.nationality = "English"
```

#### Methods

Adding a new method to an existing object is easy:

```js
myFather.fullName = function () {
  return this.firstName + " " + this.lastName
}
```

### 2. Adding to a Constructor

#### Prototypes

All objects inherit properties and methods from a prototype: `Date`, `Array`, `Person`.

The `Object.prototype` is on the top of the prototype inheritance chain: `Date` objects, `Array` objects, and `Person` objects inherit from `Object.prototype`.

#### Properties

The `prototype` property allows you to add new properties to object constructors:

```js
Person.prototype.nationality = "English"
```

#### Methods

The `prototype` property also allows you to add new methods to objects constructors:

```js
Person.prototype.fullName = function() {
  return this.firstName + " " + this.lastName
}
```

## 3 Sets

A Set is a collection of unique values.

Each value can only occur once in a Set.

#### Example

```js
// Create a Set
const letters = new Set()
const letterArray = new Set(["a", "b", "c"])

// Add a Value to the Set
letters.add("a")

// Create a Variable
const b = "b"

// Add a Variable to the Set
letters.add(b)

// If you add equal elements, only the first will be saved:
letters.add("c")

// These two won't be added
letters.add("c")
letters.add("c")
}
```

### 1. The `forEach()` and `values()` Methods

#### Example

```js
const letters = new Set(["a", "b", "c"])
let text

// List all entries
text = ""
letters.forEach (function(value) {
  text += value
})
// Now text === "abc"

// The values() method returns an [object Set Iterator] that contains all values in a Set:
text = ""
for (const entry of letters.values()) {
  text += entry
}
// Now text === "abc"
```

### 2. The `keys()` and `entries()` Methods

A Set has no keys.

`keys()` returns the same as `values()`.

`entries()` returns [value, value] pairs instead of [key, value] pairs.

This makes Sets compatible with Maps.

## 4 Maps

A Map holds key-value pairs where the keys can be any datatype.

A Map remembers the original insertion order of the keys.

#### Example

```js
// Create a Map
const fruits = new Map()
const fruitsMarket = new Map([
  ["apples", 500],
  ["bananas", 300],
  ["oranges", 200]
])

// Set Map Values
fruits.set("apples", 1000)
fruits.set("bananas", 300)
fruits.set("oranges", 200)

// Change existing Map Values
fruits.set("apples", 500)

// Get the value of a key in a Map
let apples = fruits.get("apples")
// apples = 500
```

### 1. Methods

```js
// Create a Map
const fruits = new Map([
  ["apples", 500],
  ["bananas", 300],
  ["oranges", 200]
])
let text

// List all entries
text = ""
// Remember, the parameters are in the reverse order, which means first value, then key
fruits.forEach (function(value, key) {
  text += key + ' = ' + value + " "
})
// Now text === "apples = 500 bananas = 300 oranges = 200"

// List all entries
text = ""
for (const x of fruits.entries()) {
  text += x + " "
}
// Now text === "apples,500 bananas,300 oranges,200"

// List all keys
text = ""
for (const x of fruits.keys()) {
  text += x + " "
}
// Now text === "apples bananas oranges"

// Find the sum of all values
let sum = 0
for (const x of fruits.values()) {
  sum += x
}
// Now sum = 1000
```
