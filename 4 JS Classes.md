# JS Classes

#### Example

```js
class Car {
  constructor(name, year) {
    this.name = name
    this.year = year
  }
}
```

## 1 The Constructor Method

The constructor method is a special method:

- It has to have the exact name "constructor"
- It is executed automatically when a new object is created
- It is used to initialize object properties
- If you do not define a constructor method, JS will add an empty constructor method.

Always add a `constructor()` method when creating a class.

## 2 Static Methods

Static methods are defined on the class itself.

You cannot call a `static` method on an object, only on a class.

If you want to use an object inside the `static` method, you can send it as a parameter:

```js
class Car {
  constructor(name) {
    this.name = name
  }
  static hello(myCar) {
    return "Hello " + myCar.name
  }
}

const myCar = new Car("Ford")
document.getElementById("demo").innerHTML = Car.hello(myCar)
```
