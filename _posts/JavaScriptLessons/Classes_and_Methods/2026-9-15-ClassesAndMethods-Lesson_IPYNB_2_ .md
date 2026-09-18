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
// A class is a blueprint for creating Player objects.
class Player {
  // The constructor runs when a new Player object is created.
  // health and maxHealth receive the starting values.
  // This constructor runs when a new Player is created.
  constructor(health, maxHealth) {
    // this.health and this.maxHealth are properties of this player.
    this.health = health;
    this.maxHealth = maxHealth;
  }
}
```

The `Player` class is our blueprint. `health` and `maxHealth` are properties that store information about the player.

### 2. Adding a Method

```javascript
// This class includes a method that changes the player's health.
class Player {
  // Set the starting health and the health limit.
  constructor(health, maxHealth) {
    this.health = health;
    this.maxHealth = maxHealth;
  }

  // A method is an action that a Player object can perform.
  heal() {
    // Add 10 health to the current health.
    this.health += 10;

    // Do not allow health to go above the maximum.
    if (this.health > this.maxHealth) {
      this.health = this.maxHealth;
    }
  }
}
```

The `heal()` method increases the player's health by 10. The `if` statement makes sure the health does not go above the maximum.

### 3. Creating an Object

```javascript
// Create a Player object with 80 health and a maximum of 100 health.
let player = new Player(80, 100);

// Call the heal method. The player's health changes from 80 to 90.
player.heal();

// Read the health property and print its value.
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
// Define the class, which is the blueprint for every Player object.
class Player {
  // The constructor sets the starting values for one player.
  // health and maxHealth are constructor parameters.
  constructor(health, maxHealth) {
    // this.health and this.maxHealth are properties on the new object.
    this.health = health;
    this.maxHealth = maxHealth;
  }

  // Increase the player's health by 10, without passing maxHealth.
  heal() {
    this.health += 10;
    if (this.health > this.maxHealth) {
      this.health = this.maxHealth;
    }
  }

  // Decrease the player's health by 10, without going below 0.
  takeDamage() {
    this.health -= 10;
    if (this.health < 0) {
      this.health = 0;
    }
  }
}

// Create an object from the Player class.
// The constructor receives 50 as health and 100 as maxHealth.
// Create the player object with 50 health and a maximum of 100.
let player = new Player(50, 100);

// Heal changes the health from 50 to 60.
player.heal();
// Print the current health: 60.
console.log(player.health);

// Take damage changes the health from 60 back to 50.
player.takeDamage();
// Print the current health: 50.
console.log(player.health);
{% endcapture %}

{% capture source0 %}
```javascript
%%js
//CODE_RUNNER: Predict the player's health after healing and taking damage, then run the code.
class Player {
  // This constructor runs when a new Player is created.
  constructor(health, maxHealth) {
    // Save the starting values as properties on this player.
    this.health = health;
    this.maxHealth = maxHealth;
  }

  // Increase health, but stop at maxHealth.
  heal() {
    this.health += 10;
    if (this.health > this.maxHealth) {
      this.health = this.maxHealth;
    }
  }

  // Decrease health, but stop at 0.
  takeDamage() {
    this.health -= 10;
    if (this.health < 0) {
      this.health = 0;
    }
  }
}

// Create the player object with 50 health and a maximum of 100.
let player = new Player(50, 100);
// These method calls print 60 and then 50.
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
// Player is a blueprint for a game character.
class Player {
  // Set the starting health and the health limit.
  constructor(health, maxHealth) {
    this.health = health;
    this.maxHealth = maxHealth;
  }

  // Increase health by 10, but do not exceed maxHealth.
  heal() {
    this.health += 10;
    if (this.health > this.maxHealth) {
      this.health = this.maxHealth;
    }
  }

  // Decrease health by 10, but do not go below 0.
  takeDamage() {
    this.health -= 10;
    if (this.health < 0) {
      this.health = 0;
    }
  }
}

// Start with 20 health and a maximum of 100.
let player = new Player(20, 100);

// 20 -> 30 -> 40 -> 30.
player.heal();
player.heal();
player.takeDamage();
// Print the final health: 30.
console.log(player.health);
{% endcapture %}

{% capture source1 %}
```javascript
%%js
//CODE_RUNNER: Change the starting health to 20. Predict the final health, then run the code.
// Player is a blueprint for a game character.
class Player {
  // The constructor receives the starting health and maximum health.
  constructor(health, maxHealth) {
    this.health = health;
    this.maxHealth = maxHealth;
  }

  // Add 10 health, but never exceed the maximum.
  heal() {
    this.health += 10;
    if (this.health > this.maxHealth) {
      this.health = this.maxHealth;
    }
  }

  // Remove 10 health, but never go below zero.
  takeDamage() {
    this.health -= 10;
    if (this.health < 0) {
      this.health = 0;
    }
  }
}

// Create the player object with 20 starting health.
// Create the object with 20 starting health.
let player = new Player(20, 100);
// Run the methods in order: heal, heal, then take damage.
player.heal();
player.heal();
player.takeDamage();
// The final value is 30.
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
// Step 1: Create a class for your character.
// class Character {
//   Step 2: Add a constructor with at least two parameters.
//   constructor(propertyOne, propertyTwo) {
//     Step 3: Save the parameters as object properties.
//     this.propertyOne = propertyOne;
//     this.propertyTwo = propertyTwo;
//   }
//
//   Step 4: Add one method that increases a value.
//   increaseValue() {
//     this.propertyOne += 1;
//   }
//
//   Step 5: Add one method that decreases a value.
//   decreaseValue() {
//     this.propertyOne -= 1;
//   }
// }
//
// Step 6: Create an object with new and call both methods.
{% endcapture %}

{% capture source2 %}
```javascript
%%js
//CODE_RUNNER: Create your own game character class with at least two properties and two methods.
// Use the steps below as a guide for your own solution.
// 1. Define a class.
// 2. Add a constructor with two properties.
// 3. Add one method that increases a value.
// 4. Add one method that decreases a value.
// 5. Create an object with new and test both methods.
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
// Player is the blueprint for the game character.
class Player {
  // health and coins are the starting values passed to the constructor.
  constructor(health, coins) {
    // Store both values as properties on the player object.
    this.health = health;
    this.coins = coins;
  }

  // Increase the number of coins by 1.
  collectCoin() {
    this.coins += 1;
  }

  // Decrease the player's health by 10.
  takeDamage() {
    this.health -= 10;
  }
}

// Create a Player object with 100 health and 0 coins.
let player = new Player(100, 0);

// Use both methods to change the object's properties.
player.collectCoin();
player.takeDamage();

// The output is 90 health and 1 coin.
console.log(player.health);
console.log(player.coins);
```


{% capture challenge3 %}
Homework: Create your own game character class with at least two methods.
{% endcapture %}

{% capture code3 %}
// Define a class, which is a blueprint for game character objects.
class Player {
  // The constructor sets the starting health and coin count.
  constructor(health, coins) {
    // Store the starting values as object properties.
    this.health = health;
    this.coins = coins;
  }

  // This method increases the number of coins.
  collectCoin() {
    this.coins += 1;
  }

  // This method decreases the player's health.
  takeDamage() {
    this.health -= 10;
  }
}

// Create an object using the Player class.
let player = new Player(100, 0);

// Call the methods to update the player's properties.
player.collectCoin();
player.takeDamage();

// Print the updated values: 90 health and 1 coin.
console.log(player.health);
console.log(player.coins);
{% endcapture %}

{% capture source3 %}
```javascript
%%js
//CODE_RUNNER: Homework: Create your own game character class with at least two methods.
// This example shows one possible completed solution.
class Player {
  // Set the starting health and number of coins.
  constructor(health, coins) {
    // Save the values as properties on the new object.
    this.health = health;
    this.coins = coins;
  }

  // Increase coins by 1.
  collectCoin() {
    this.coins += 1;
  }

  // Decrease health by 10.
  takeDamage() {
    this.health -= 10;
  }
}

// Create a Player object with 100 health and 0 coins.
let player = new Player(100, 0);
// Change the object by calling its methods.
player.collectCoin();
player.takeDamage();
// Print the final values: 90 and 1.
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

