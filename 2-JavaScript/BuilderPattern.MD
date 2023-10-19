
# Builder Pattern in JavaScript


## Definition
The Builder Pattern is a design pattern in JavaScript that focuses on building complex objects step by step. It separates the construction of an object from its representation, allowing you to create different variations of an object while keeping the construction process consistent.

## Explanation in Simple Terms
Think of the Builder Pattern as assembling a custom-made sandwich. Instead of making the entire sandwich at once, you start by selecting the type of bread, then add your choice of ingredients, such as lettuce, cheese, and meat, and finally, you pick the sauce. This way, you can create a variety of sandwiches with different ingredients, but the process of building each one remains the same.

In JavaScript, the Builder Pattern allows you to create complex objects by breaking down the construction into smaller, manageable steps. It's particularly useful when you need to create objects with multiple optional or interchangeable components.


## Code Related Explanation

Here's an example of how you can implement the Builder Pattern in JavaScript:

```bash
// Product: A complex object to be built
class Sandwich {
  constructor() {
    this.bread = null;
    this.ingredients = [];
    this.sauce = null;
  }

  describe() {
    console.log(`Delicious sandwich with ${this.ingredients.join(', ')} on ${this.bread} bread, topped with ${this.sauce}.`);
  }
}

// Builder: An abstract builder interface
class SandwichBuilder {
  setBread() {}
  addIngredients() {}
  addSauce() {}
  build() {}
}

// Concrete Builder: Constructs a specific type of sandwich
class VeggieSandwichBuilder extends SandwichBuilder {
  setBread() {
    this.sandwich.bread = 'whole wheat';
  }

  addIngredients() {
    this.sandwich.ingredients.push('lettuce', 'tomato', 'onion', 'cheese');
  }

  addSauce() {
    this.sandwich.sauce = 'mayo and mustard';
  }

  build() {
    this.sandwich = new Sandwich();
    this.setBread();
    this.addIngredients();
    this.addSauce();
    return this.sandwich;
  }
}

// Director: Manages the construction process
class SandwichDirector {
  constructor(builder) {
    this.builder = builder;
  }

  construct() {
    return this.builder.build();
  }
}

// Example usage
const veggieBuilder = new VeggieSandwichBuilder();
const sandwichDirector = new SandwichDirector(veggieBuilder);

const customVeggieSandwich = sandwichDirector.construct();
customVeggieSandwich.describe();
```
In this code:

- Sandwich is the product class, representing the complex object to be built.
- SandwichBuilder is an abstract builder interface, which concrete builders must implement.
- VeggieSandwichBuilder is a concrete builder that constructs a specific type of sandwich (in this case, a veggie sandwich).
- SandwichDirector manages the construction process, taking a builder as input and orchestrating the steps.

By using the Builder Pattern, you can create custom sandwiches with different combinations of ingredients and sauces while keeping the construction process consistent and easily extendable.

