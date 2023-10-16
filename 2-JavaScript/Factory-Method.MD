# Design Pattern - Factory Method in JavaScript

## Definition

The Factory Method is a design pattern in JavaScript that provides an interface for creating objects but allows subclasses to alter the type of objects that will be created. It promotes loose coupling between the creator and the products, enabling you to create objects without specifying the exact class of object that will be created.

## Explanation in Simple Terms

Think of the Factory Method as a magic factory where you don't know exactly what it's going to produce, but you're sure it will give you something you need. You, as a developer, define the general rules of what should be created, and then, different parts of your code can decide what specific items should be made without affecting each other.

For instance, imagine you're a toy manufacturer. You have a toy factory, and the factory knows how to produce toys. The factory is like a "Factory Method." You tell the factory that you need a toy, but you don't specify the exact type. The factory decides whether to make a teddy bear, a robot, or any other toy. This way, you can change the type of toy without changing how you ask for a toy.

## Code Related Explanation

Here's a simple example of a Factory Method in JavaScript:

```javascript
// Factory Method
function createProduct(type) {
    if (type === 'A') {
        return new ConcreteProductA();
    } else if (type === 'B') {
        return new ConcreteProductB();
    }
}

// Concrete Products
class ConcreteProductA {
    operation() {
        return 'Product A';
    }
}

class ConcreteProductB {
    operation() {
        return 'Product B';
    }
}

// Usage
const product1 = createProduct('A');
console.log(product1.operation()); // Output: Product A

const product2 = createProduct('B');
console.log(product2.operation()); // Output: Product B
```

