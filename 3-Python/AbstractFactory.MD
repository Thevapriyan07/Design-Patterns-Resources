# Python Abstract Factory Design Pattern

## Table of Contents

- [Definition](#definition)
- [Explanation in Simple Terms](#explanation-in-simple-terms)
- [Code Related Explanation](#code-related-explanation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Definition

The Abstract Factory Design Pattern is a creational design pattern that provides an interface for creating families of related or dependent objects without specifying their concrete classes. It's used to create objects that are related and should work together, ensuring that they are compatible.

## Explanation in Simple Terms

Imagine you're at a car factory. You have two main components: the body of the car and the engine. In an Abstract Factory, you can choose different "factories" to produce compatible sets of car bodies and engines. This ensures that the body and engine always work well together, and you can easily switch between different sets of components.

## Code Related Explanation

In this repository, we've provided a Python example to demonstrate the Abstract Factory Design Pattern. We have abstract classes for creating `CarBody` and `CarEngine`. Concrete factories, such as `SedanFactory` and `SUVFactory`, produce related sets of `CarBody` and `CarEngine` objects. This pattern allows you to create and use compatible sets of objects that work together seamlessly.

## Usage

You can use this repository to understand how the Abstract Factory Design Pattern works in Python. Clone the repository and explore the code to see how the pattern is implemented.

```python
# Example usage:
factory = SedanFactory()  # or SUVFactory()
body = factory.create_car_body()
engine = factory.create_car_engine()
