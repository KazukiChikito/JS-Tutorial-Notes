# JS Classes

JavaScript Classes are templates for JavaScript Objects.

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

## 2 Inheritance

To create a class inheritance, use the `extends` keyword.

A class created with a class inheritance inherits all the methods from another class:

```js
class Car {
  constructor(brand) {
    this.carBrand = brand;
  }
  present() {
    return 'I have a ' + this.carBrand;
  }
}

class Model extends Car {
  constructor(brand, model) {
    super(brand);
    this.carModel = model;
  }
  show() {
    return this.present() + ', it is a ' + this.carModel;
  }
}

let myCar = new Model("Ford", "Mustang");
document.getElementById("demo").innerHTML = myCar.show();
```

The `super()` method calls the parent's constructor method and lets us get access to the parent's properties and methods.

>Inheritance is useful for code reusability: reuse properties and methods of an existing class when you create a new class.

## 3 Static Methods

Static methods are defined on the class itself.

You cannot call a `static` method on an object, only on a class.

```js
class Car {
  constructor(name) {
    this.name = name;
  }
  static hello() {
    return "Hello!!";
  }
}

const myCar = new Car("Ford");

// You can call 'hello()' on the Car Class:
document.getElementById("demo").innerHTML = Car.hello();

// But not on a Car Object:
// document.getElementById("demo").innerHTML = myCar.hello();
// this will raise an error.
```

If you want to use an object inside the `static` method, you can send it as a parameter:

```js
class Car {
  constructor(name) {
    this.name = name
  }
  static hello(car) {
    return "Hello " + car.name
  }
}

const myCar = new Car("Ford")
document.getElementById("demo").innerHTML = Car.hello(myCar)
```
