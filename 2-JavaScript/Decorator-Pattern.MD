# Decorator Pattern in JavaScript

## Definition
The Decorator Pattern is a structural design pattern that allows you to add new behaviors or responsibilities to objects without altering their existing code. It is typically used to extend the functionalities of classes dynamically at runtime.

## Explanation in Simple Terms
Think of the Decorator Pattern as adding layers or wrappers to an object like you would decorate a Christmas tree. Each layer can add new features or functionality without changing the tree itself. For example, you can add lights, ornaments, and tinsel to a bare tree, and you can remove or change these decorations as you please.

In software terms, the Decorator Pattern allows you to take an object and add new features to it without modifying the original object's code. This helps keep your codebase flexible and easy to maintain, as you can attach or detach responsibilities as needed.

## Code Related Explanation
In JavaScript, you can implement the Decorator Pattern using a combination of objects and functions. Here's a simple example to illustrate the concept:
```
// The base object
class Coffee {
  cost() {
    return 5;
  }
}

// Decorator 1: Milk
class MilkDecorator {
  constructor(coffee) {
    this.coffee = coffee;
  }

  cost() {
    return this.coffee.cost() + 2;
  }
}

// Decorator 2: Sugar
class SugarDecorator {
  constructor(coffee) {
    this.coffee = coffee;
  }

  cost() {
    return this.coffee.cost() + 1;
  }
}

// Usage
const plainCoffee = new Coffee();
console.log("Cost of plain coffee:", plainCoffee.cost()); // Output: 5

const coffeeWithMilk = new MilkDecorator(plainCoffee);
console.log("Cost of coffee with milk:", coffeeWithMilk.cost()); // Output: 7

const coffeeWithMilkAndSugar = new SugarDecorator(coffeeWithMilk);
console.log("Cost of coffee with milk and sugar:", coffeeWithMilkAndSugar.cost()); // Output: 8
```
