# Python Factory Method Design Pattern

## Table of Contents

- [Definition](#definition)
- [Explanation in Simple Terms](#explanation-in-simple-terms)
- [Code Related Explanation](#code-related-explanation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Definition

The Factory Method is a creational design pattern that provides an interface for creating objects but allows subclasses to alter the type of objects that will be created. It defines an interface for creating an object, but it is the responsibility of the derived class, or factory, to implement this method and decide which class to instantiate.

## Explanation in Simple Terms

Imagine you have a base class with a method to create objects, but the specific type of object isn't known in the base class. Instead, it's determined by subclasses. The Factory Method pattern lets you delegate the responsibility of creating objects to these subclasses. It's like a "factory" that produces different types of objects based on what the client code needs.

## Code Related Explanation

In this repository, we have provided a simple Python example to demonstrate the Factory Method pattern. We have defined a base class `Product` with a factory method `create`. Two concrete classes, `ConcreteProductA` and `ConcreteProductB`, inherit from `Product` and override the `create` method. The `create_product` function acts as the factory method, creating instances of the appropriate concrete product based on the type specified.

## Usage

You can use this repository to understand how the Factory Method pattern works in Python. Clone the repository and explore the code to see how the pattern is implemented.

```python
# Example usage:
product_a = create_product("A")
product_b = create_product("B")

