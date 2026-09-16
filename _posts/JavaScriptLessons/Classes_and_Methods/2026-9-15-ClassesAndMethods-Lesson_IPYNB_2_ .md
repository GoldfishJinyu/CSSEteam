---
layout: post
categories: ['CSSE JavaScript']
microblog: False
codemirror: True
title: Classes and Methods
description: Basics of Classes and Methods
permalink: /js/classes
author: Jailene Tang
---

## JavaScript Classes and Methods: Designing a Cake

## What are Classes and Methods? (1-Minute Explanation)

In JavaScript, a **class** is like a blueprint for creating objects. It tells us what information an object has and what it can do.

A **method** is a function inside a class. Methods allow an object to perform an action.

In a bakery, we can create a `Cake` class. A cake can have information such as its flavor, price, and number of slices. The cake can also perform actions, such as changing its flavor or changing its price.

JavaScript uses a `constructor` to give an object its starting values.

- **Class:** The blueprint for an object.
- **Constructor:** Sets the starting information.
- **Property:** Stores information about the object.
- **Method:** An action the object can perform.
- **Object:** A real object created from the class.

For example, we can create a chocolate cake that costs $20 and has 8 slices.

## Example: Creating a Cake

### 1. Creating the Class

```javascript
class Cake {
  constructor(flavor, price, slices) {
    this.flavor = flavor;
    this.price = price;
    this.slices = slices;
  }
}
```

The `Cake` class is our blueprint. `flavor`, `price`, and `slices` are properties that store information about the cake.

### 2. Adding Methods

```javascript
class Cake {
  constructor(flavor, price, slices) {
    this.flavor = flavor;
    this.price = price;
    this.slices = slices;
  }

  changeFlavor(newFlavor) {
    this.flavor = newFlavor;
  }

  changePrice(newPrice) {
    this.price = newPrice;
  }
}
```

The `changeFlavor()` method changes the cake's flavor. The `changePrice()` method changes the cake's price.

### 3. Creating an Object

```javascript
let cake = new Cake("Chocolate", 20, 8);

cake.changeFlavor("Strawberry");

console.log(cake.flavor);
```

The cake starts as **Chocolate**. After using `changeFlavor()`, the flavor becomes **Strawberry**.

## 5-Minute Interactive: Design Your Cake

Your cake starts with a Chocolate flavor, a price of $20, and 8 slices. Customers can request changes to the flavor or price.



{% capture challenge0 %}
Predict what the Cake code will print, then run it. What are the final flavor and price?
{% endcapture %}

{% capture code0 %}
class Cake {
  constructor(flavor, price, slices) {
    this.flavor = flavor;
    this.price = price;
    this.slices = slices;
  }

  changeFlavor(newFlavor) {
    this.flavor = newFlavor;
  }

  changePrice(newPrice) {
    this.price = newPrice;
  }
}

let cake = new Cake("Chocolate", 20, 8);
cake.changeFlavor("Strawberry");
console.log(cake.flavor);
cake.changePrice(25);
console.log(cake.price);
{% endcapture %}

{% capture source0 %}
```javascript
%%js
//CODE_RUNNER: Predict what the Cake code will print, then run it.
class Cake {
  constructor(flavor, price, slices) {
    this.flavor = flavor;
    this.price = price;
    this.slices = slices;
  }

  changeFlavor(newFlavor) {
    this.flavor = newFlavor;
  }

  changePrice(newPrice) {
    this.price = newPrice;
  }
}

let cake = new Cake("Chocolate", 20, 8);
cake.changeFlavor("Strawberry");
console.log(cake.flavor);
cake.changePrice(25);
console.log(cake.price);
```
{% endcapture %}

{% include runners/code.html
   runner_id="js-classes-0"
   language="javascript"
   challenge=challenge0
   code=code0
   source=source0
%}




{% capture challenge1 %}
Start with a Vanilla cake. Predict the final flavor and price before running the code.
{% endcapture %}

{% capture code1 %}
class Cake {
  constructor(flavor, price, slices) {
    this.flavor = flavor;
    this.price = price;
    this.slices = slices;
  }

  changeFlavor(newFlavor) {
    this.flavor = newFlavor;
  }

  changePrice(newPrice) {
    this.price = newPrice;
  }
}

let cake = new Cake("Vanilla", 15, 6);
cake.changeFlavor("Strawberry");
cake.changePrice(18);
console.log(cake.flavor);
console.log(cake.price);
{% endcapture %}

{% capture source1 %}
```javascript
%%js
//CODE_RUNNER: Start with a Vanilla cake. Predict the final flavor and price.
class Cake {
  constructor(flavor, price, slices) {
    this.flavor = flavor;
    this.price = price;
    this.slices = slices;
  }

  changeFlavor(newFlavor) {
    this.flavor = newFlavor;
  }

  changePrice(newPrice) {
    this.price = newPrice;
  }
}

let cake = new Cake("Vanilla", 15, 6);
cake.changeFlavor("Strawberry");
cake.changePrice(18);
console.log(cake.flavor);
console.log(cake.price);
```
{% endcapture %}

{% include runners/code.html
   runner_id="js-classes-1"
   language="javascript"
   challenge=challenge1
   code=code1
   source=source1
%}




{% capture challenge2 %}
Bonus challenge: What will the cake's final flavor and price be?
{% endcapture %}

{% capture code2 %}
class Cake {
  constructor(flavor, price, slices) {
    this.flavor = flavor;
    this.price = price;
    this.slices = slices;
  }

  changeFlavor(newFlavor) {
    this.flavor = newFlavor;
  }

  changePrice(newPrice) {
    this.price = newPrice;
  }
}

let cake = new Cake("Vanilla", 15, 6);
cake.changeFlavor("Matcha");
cake.changePrice(22);
cake.changeFlavor("Chocolate");
console.log(cake.flavor);
console.log(cake.price);
{% endcapture %}

{% capture source2 %}
```javascript
%%js
//CODE_RUNNER: Bonus challenge: What will the cake's final flavor and price be?
class Cake {
  constructor(flavor, price, slices) {
    this.flavor = flavor;
    this.price = price;
    this.slices = slices;
  }

  changeFlavor(newFlavor) {
    this.flavor = newFlavor;
  }

  changePrice(newPrice) {
    this.price = newPrice;
  }
}

let cake = new Cake("Vanilla", 15, 6);
cake.changeFlavor("Matcha");
cake.changePrice(22);
cake.changeFlavor("Chocolate");
console.log(cake.flavor);
console.log(cake.price);
```
{% endcapture %}

{% include runners/code.html
   runner_id="js-classes-2"
   language="javascript"
   challenge=challenge2
   code=code2
   source=source2
%}


## Homework



{% capture challenge3 %}
Homework Challenge - Create a new cake class with at least two methods.
{% endcapture %}

{% capture code3 %}
//Try adding a method that changes the number of slices or adds a topping.
{% endcapture %}

{% capture source3 %}
```javascript
%%js
//CODE_RUNNER: Create a new cake class with at least two methods.
//Try adding a method that changes the number of slices or adds a topping.

```
{% endcapture %}

{% include runners/code.html
   runner_id="js-classes-3"
   language="javascript"
   challenge=challenge3
   code=code3
   source=source3
%}

