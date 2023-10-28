# Design Pattern: Builder

## Table of Contents
- [Definition](#definition)
- [Explanation in Simple Terms](#explanation-in-simple-terms)
- [Code-Related Explanation](#code-related-explanation)

## Definition
The Builder pattern is a creational design pattern that separates the construction of a complex object from its representation. It allows you to create an object step by step, with control over its various features and configurations. This pattern is particularly useful when you need to create complex objects with multiple optional components or configurations.

## Explanation in Simple Terms
Imagine you're building a custom pizza. Instead of telling the pizzeria all the details at once, you can use the Builder pattern. First, you choose the type of crust, then the sauce, add some toppings, and finally, specify the cooking time. The Builder pattern lets you build your pizza step by step, customizing it to your preferences. It's like a recipe where you choose the ingredients and the order to create a delicious dish.

In software, this pattern is used when you have a complex object with many options and configurations. Instead of overwhelming yourself with one big constructor, you use a builder to set each option one at a time.

## Code-Related Explanation
In Java, the Builder pattern is typically implemented by creating a static inner class (the builder) within the class of the object you want to construct. The builder class provides methods for setting the object's properties and returns the constructed object when it's ready. This way, you can chain method calls to set various attributes in a fluent and readable manner.

Here's a basic code structure for the Builder pattern in Java:

```java
// Product class
class Pizza {
    private String crust;
    private String sauce;
    private String toppings;
    private int cookingTime;

    // Private constructor to prevent direct instantiation
    private Pizza() {}

    // Builder class
    static class Builder {
        private Pizza pizza = new Pizza();

        public Builder crust(String crust) {
            pizza.crust = crust;
            return this;
        }

        public Builder sauce(String sauce) {
            pizza.sauce = sauce;
            return this;
        }

        public Builder toppings(String toppings) {
            pizza.toppings = toppings;
            return this;
        }

        public Builder cookingTime(int cookingTime) {
            pizza.cookingTime = cookingTime;
            return this;
        }

        public Pizza build() {
            return pizza;
        }
    }
}

// Example usage
Pizza customPizza = new Pizza.Builder()
    .crust("Thin")
    .sauce("Tomato")
    .toppings("Mushrooms, Pepperoni")
    .cookingTime(15)
    .build();
