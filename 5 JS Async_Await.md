# JS Async/Await

## 1 Callbacks

A callback is a function passed as an argument to another function.

This technique allows a function to call another function.

A callback function can run after another function has finished.

#### Example

```js
function myDisplay(value) {
  document.getElementById("demo").innerHTML = value
}

// Using myDisplay as a callback function, passed to myCalculator() as an argument
function myCalculator(num1, num2, myCallback) {
  let sum = num1 + num2
  myCallback(sum)
}

myCalculator(5, 5, myDisplay)
```

## 2 Asynchronous

Functions running in parallel with other functions are called asynchronous.

### 1. The `setTimeOut()` Function

When using `setTimeout()`, you can specify a callback function to be executed after an amount of time.

#### Example

```js
function myDisplay(value) {
  document.getElementById("demo").innerHTML = value
}

setTimeout(function() { myDisplay("I love You !!!") }, 3000)
```

### 2. The `setInterval()` Function

When using `setInterval()`, you can specify a callback function to be executed for each interval.

#### Example

```js
function myClock() {
  let d = new Date()
  document.getElementById("demo").innerHTML = 
  d.getHours() + ":" +
  d.getMinutes() + ":" +
  d.getSeconds()
}

// myClock() will be called every second.
setInterval(myClock, 1000)
```

>With asynchronous programming, JS programs can start long-running tasks, and continue running other tasks in parallel.
>But, asynchronus programs are difficult to write and difficult to debug.
>Therefore, most modern asynchronous JS methods don't use callbacks. They use **Promises** instead.

## 3 Promises

### 1. The Promise object:

The Promise object contains a function, which itself contains 2 callbacks as ***parameters***. The first callback will be called when the code is a success. The second callback will be called when the code is an error.

The `then()` method takes two callback as ***arguments***. These are the actual functions to the placeholder callbacks aforementioned in the Promise object.

#### Example

```js
const myFulfill = (value) => { 
  // Code if success
  document.getElementById("demo").innerHTML = value
}
const myReject = (error) => { 
  // Code if error
  document.getElementById("demo").innerHTML = error
}

const myPromiseFunction = (ful, rej) => {
  // "Producing Code" (can take some time)
  let x = 0
  if (x == 0) {
    ful("OK") // when success
  } else {
    rej("Error") // when error
  }
}

let myPromise = new Promise(myPromiseFunction)

// "Consuming Code" (must wait for a pending Promise)
myPromise.then(myFulfill, myReject)
```

### 2. Callback vs. Promise

#### Waiting for a Timeout

Using Callback:

```js
let myDisplay = (value) => { document.getElementById("demo").innerHTML = value }

setTimeout( () => { myDisplay("I love You !!!") }, 3000)
```

Using Promise:

```js
let myFulfill = (value) => { document.getElementById("demo").innerHTML = value }

let myPromise = new Promise( (ful) => {
  setTimeout(function() { ful("I love You !!!") }, 3000)
})

myPromise.then(myFulfill)
```

#### Waiting for a File

Using Callback:

```js
let myDisplay() = (value) => { document.getElementById("demo").innerHTML = value }

let getFile = (myCallback) => {
  let req = new XMLHttpRequest()
  req.open('GET', "https://kazukichikito.github.io/Ngotchi-The-Band/index.html")
  req.onload = () => {
    if (req.status == 200) {
      myCallback(req.responseText)
    } else {
      myCallback("Error: " + req.status)
    }
  }
  req.send()
}

getFile(myDisplay)
```

Using Promise:

```js
let myDisplay() = (value) => { document.getElementById("demo").innerHTML = value }

let myPromise = new Promise(function(ful, rej) {
  let req = new XMLHttpRequest()
  req.open('GET', "https://kazukichikito.github.io/Ngotchi-The-Band/index.html")
  req.onload = function() {
    if (req.status == 200) {
      ful(req.response)
    } else {
      rej("Error: " + req.status)
    }
  }
  req.send()
})

myPromise.then(
  (value) => { myDisplay(value)},
  (error) => { myDisplay(error)}
)
```

## 4 Async/Await

### 1. Async

The keyword `async` before a function makes the function return a promise.

#### Example

```js
// This
async function myAsyncFunction() {
  return "Hello"
}

// ...is the same as this
function myPromise() {
  return Promise.resolve("Hello")
}
```

### 2. Await

The `await` keyword can only be used inside an `async` function.

The `await` keyword makes the function pause the execution and wait for a resolved promise before it continues.

#### Example

```js
async function myAADisplay() {
  let myPromise = new Promise(function(ful) {
    setTimeout(function() {ful("I love You !!")}, 3000)
  })
  document.getElementById("demo").innerHTML = await myPromise
}

myAADisplay()
```
