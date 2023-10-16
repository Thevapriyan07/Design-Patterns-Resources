# Prototype Pattern in JavaScript

## Definition:

The Prototype Pattern is a creational design pattern in JavaScript. It allows you to create new objects by copying an existing object, often referred to as the prototype. In JavaScript, this pattern leverages the prototypal inheritance model. Instead of creating new objects from constructors, you create new objects by cloning an existing object, inheriting its properties and methods.

## Explanation in Simple Terms:

Think of the Prototype Pattern as making a photocopy of a master document. You start with a prototype, which is like your master document, and you can make as many copies as you need. These copies inherit everything from the prototype. In JavaScript, it's like creating a new object that's linked to an existing object, so any changes in the original reflect in the copies and vice versa.

It's a handy way to create new objects that share common attributes and behaviors without creating a separate constructor function for each. You can think of it as object cloning.

## Code-Related Explanation:

The Prototype Pattern in JavaScript is based on object cloning through the prototype chain. Here's a simplified example:

```JavaScript 
// Step 1: Create a prototype object
const carPrototype = {
    make: 'Unknown',
    model: 'Unknown',
    start: function() {
        console.log('Starting the ' + this.make + ' ' + this.model);
    }
};

// Step 2: Create new objects by cloning the prototype
const car1 = Object.create(carPrototype);
car1.make = 'Toyota';
car1.model = 'Camry';

const car2 = Object.create(carPrototype);
car2.make = 'Honda';
car2.model = 'Civic';

// Step 3: Use the objects
car1.start(); // Output: Starting the Toyota Camry
car2.start(); // Output: Starting the Honda Civic

```