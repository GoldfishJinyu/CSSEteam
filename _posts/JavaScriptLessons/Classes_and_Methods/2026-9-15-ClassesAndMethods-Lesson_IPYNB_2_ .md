---
layout: post
categories: ['CSSE JavaScript']
microblog: False
codemirror: True
title: Classes and Methods
description: Basics of Classes and Methods
permalink: /js/classes
author: Jailene and Aroosh
---

## JavaScript Classes and Methods: Building a Game Character

### Lesson Plan
**Learning Objective:** By the end of this lesson, you will be able to create a simple JavaScript class with properties and methods, then use methods to change an object’s information.

**Success Criteria:** You can create a class using a constructor, identify its properties and methods, create an object using `new`, and use its methods to change the object's properties.

<h1 class="lesson-important-title">What are Classes and Methods? (1-Min Explanation)</h1>

In JavaScript, a **class** is like a blueprint for creating objects. It tells us what information an object has and what it can do.

A **method** is a function inside a class. Methods allow an object to perform an action.

For example, in a game, we can create a `Player` class. A player can have information such as health and max health. The player can also perform actions such as healing and taking damage.

JavaScript uses a `constructor` to give an object its starting values.

- **Class:** The blueprint for an object.
- **Constructor:** Sets the starting information.
- **Property:** Stores information about the object.
- **Method:** An action the object can perform.
- **Object:** A real object created from the class.

For example, if we create a player with 80 health and a maximum of 100 health, we can use a method to heal the player.

## Example: Creating a Player

### 1. Creating the Class

```javascript
class Player {
  constructor(health, maxHealth) {
    this.health = health;
    this.maxHealth = maxHealth;
  }
}
```

The `Player` class is our blueprint. `health` and `maxHealth` are properties that store information about the player.

### 2. Adding a Method

```javascript
class Player {
  constructor(health, maxHealth) {
    this.health = health;
    this.maxHealth = maxHealth;
  }

  heal() {
    this.health += 10;

    if (this.health > this.maxHealth) {
      this.health = this.maxHealth;
    }
  }
}
```

The `heal()` method increases the player's health by 10. The `if` statement makes sure the health does not go above the maximum.

### 3. Creating an Object

```javascript
let player = new Player(80, 100);

player.heal();

console.log(player.health);
```

The player starts with 80 health. After using `heal()`, the player's health becomes 90.

<style>
  .popcorn-hack-title {
    text-shadow: none !important;
    filter: none !important;
  }

  .lesson-important-title {
    text-shadow: none !important;
    filter: none !important;
  }
</style>

<h1 class="popcorn-hack-title">Popcorn Hack: The Player Battle (5-Min Interactive)</h1>

The player starts with **50 health** and has a maximum of **100 health**. The player can heal by 10 health, take 10 damage, never have more than 100 health, and never have less than 0 health.



{% capture challenge0 %}
Predict the player's health after healing and taking damage, then run the code.
{% endcapture %}

{% capture code0 %}
class Player {
  constructor(health, maxHealth) {
    this.health = health;
    this.maxHealth = maxHealth;
  }

  heal() {
    this.health += 10;
    if (this.health > this.maxHealth) {
      this.health = this.maxHealth;
    }
  }

  takeDamage() {
    this.health -= 10;
    if (this.health < 0) {
      this.health = 0;
    }
  }
}

let player = new Player(50, 100);
player.heal();
console.log(player.health);
player.takeDamage();
console.log(player.health);
{% endcapture %}

{% capture source0 %}
```javascript
%%js
//CODE_RUNNER: Predict the player's health after healing and taking damage, then run the code.
class Player {
  constructor(health, maxHealth) {
    this.health = health;
    this.maxHealth = maxHealth;
  }

  heal() {
    this.health += 10;
    if (this.health > this.maxHealth) {
      this.health = this.maxHealth;
    }
  }

  takeDamage() {
    this.health -= 10;
    if (this.health < 0) {
      this.health = 0;
    }
  }
}

let player = new Player(50, 100);
player.heal();
console.log(player.health);
player.takeDamage();
console.log(player.health);
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
Change the starting health to 20. Predict the final health, then run the code.
{% endcapture %}

{% capture code1 %}
class Player {
  constructor(health, maxHealth) {
    this.health = health;
    this.maxHealth = maxHealth;
  }

  heal() {
    this.health += 10;
    if (this.health > this.maxHealth) {
      this.health = this.maxHealth;
    }
  }

  takeDamage() {
    this.health -= 10;
    if (this.health < 0) {
      this.health = 0;
    }
  }
}

let player = new Player(20, 100);
player.heal();
player.heal();
player.takeDamage();
console.log(player.health);
{% endcapture %}

{% capture source1 %}
```javascript
%%js
//CODE_RUNNER: Change the starting health to 20. Predict the final health, then run the code.
class Player {
  constructor(health, maxHealth) {
    this.health = health;
    this.maxHealth = maxHealth;
  }

  heal() {
    this.health += 10;
    if (this.health > this.maxHealth) {
      this.health = this.maxHealth;
    }
  }

  takeDamage() {
    this.health -= 10;
    if (this.health < 0) {
      this.health = 0;
    }
  }
}

let player = new Player(20, 100);
player.heal();
player.heal();
player.takeDamage();
console.log(player.health);
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
Create your own game character class with at least two properties and two methods. Include one method that increases a value and one that decreases a value.
{% endcapture %}

{% capture code2 %}
// Create your own game character class here.
// Include a constructor, two properties, and two methods.
{% endcapture %}

{% capture source2 %}
```javascript
%%js
//CODE_RUNNER: Create your own game character class with at least two properties and two methods.
// Create your own game character class here.
// Include a constructor, two properties, and two methods.
```
{% endcapture %}

{% include runners/code.html
    runner_id="js-classes-2"
   language="javascript"
   challenge=challenge2
   code=code2
   source=source2
%}


## Build Your Own Game Character (10-Min Homework)

Create your own JavaScript class for a `Player`, `Enemy`, `Pet`, or `Robot`.

Your class must include a constructor, at least two properties, at least two methods, one method that increases a value, one method that decreases a value, and an object created using `new`.

Example:

```javascript
class Player {
  constructor(health, coins) {
    this.health = health;
    this.coins = coins;
  }

  collectCoin() {
    this.coins += 1;
  }

  takeDamage() {
    this.health -= 10;
  }
}

let player = new Player(100, 0);
player.collectCoin();
player.takeDamage();
console.log(player.health);
console.log(player.coins);
```


{% capture challenge3 %}
Homework: Create your own game character class with at least two methods.
{% endcapture %}

{% capture code3 %}
class Player {
  constructor(health, coins) {
    this.health = health;
    this.coins = coins;
  }

  collectCoin() {
    this.coins += 1;
  }

  takeDamage() {
    this.health -= 10;
  }
}

let player = new Player(100, 0);
player.collectCoin();
player.takeDamage();
console.log(player.health);
console.log(player.coins);
{% endcapture %}

{% capture source3 %}
```javascript
%%js
//CODE_RUNNER: Homework: Create your own game character class with at least two methods.
class Player {
  constructor(health, coins) {
    this.health = health;
    this.coins = coins;
  }

  collectCoin() {
    this.coins += 1;
  }

  takeDamage() {
    this.health -= 10;
  }
}

let player = new Player(100, 0);
player.collectCoin();
player.takeDamage();
console.log(player.health);
console.log(player.coins);

```
{% endcapture %}

{% include runners/code.html
   runner_id="js-classes-3"
   language="javascript"
   challenge=challenge3
   code=code3
   source=source3
%}

