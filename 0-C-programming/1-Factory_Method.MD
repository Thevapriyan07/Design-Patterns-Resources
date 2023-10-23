# Factory Method Design Pattern in C

This repository provides an introduction to the Factory Method design pattern in C programming. This README will cover the definition, provide a simple explanation of the Factory Method pattern, and offer code-related explanations and examples.

## Table of Contents
- [Definition](#definition)
- [Explanation in Simple Terms](#explanation-in-simple-terms)
- [Code-Related Explanation](#code-related-explanation)

## Definition

The Factory Method is a creational design pattern that provides an interface for creating objects but allows subclasses to alter the type of objects that will be created. It encapsulates the object creation process and provides a way for the client code to create objects without specifying their exact class. In C, this can be implemented through function pointers and dynamic memory allocation.

## Explanation in Simple Terms

Imagine you are running a pizza restaurant, and you have a standard way of making pizzas, but you want to allow different franchises to create their own unique pizzas. The Factory Method pattern is like having a pizza factory where you define a set of steps (e.g., prepare dough, add sauce, add toppings), but each franchise can implement these steps differently to create their own pizzas. Customers can order pizzas without knowing the specific details of how they are made at each franchise.

## Code-Related Explanation

Here's a basic example in C to illustrate the Factory Method pattern:

```c
#include <stdio.h>
#include <stdlib.h>

// Define the product interface
typedef struct {
    void (*prepare)();
    void (*bake)();
} Pizza;

// Define concrete product types
typedef struct {
    Pizza base;
} CheesePizza;

typedef struct {
    Pizza base;
} PepperoniPizza;

// Define the factory method
Pizza* createPizza(int pizzaType) {
    Pizza* pizza = NULL;
    switch (pizzaType) {
        case 1:
            pizza = (Pizza*)malloc(sizeof(CheesePizza));
            pizza->prepare = cheesePizzaPrepare;
            pizza->bake = genericPizzaBake;
            break;
        case 2:
            pizza = (Pizza*)malloc(sizeof(PepperoniPizza));
            pizza->prepare = pepperoniPizzaPrepare;
            pizza->bake = genericPizzaBake;
            break;
    }
    return pizza;
}

// Define concrete implementations of prepare and bake for each pizza
void cheesePizzaPrepare() {
    printf("Preparing Cheese Pizza...\n");
}

void pepperoniPizzaPrepare() {
    printf("Preparing Pepperoni Pizza...\n");
}

void genericPizzaBake() {
    printf("Baking the Pizza...\n");
}

int main() {
    Pizza* pizza1 = createPizza(1);
    pizza1->prepare();
    pizza1->bake();
    
    Pizza* pizza2 = createPizza(2);
    pizza2->prepare();
    pizza2->bake();
    
    free(pizza1);
    free(pizza2);
    
    return 0;
}
