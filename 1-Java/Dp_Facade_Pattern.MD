# Design Pattern - Facade Pattern in Java
## Definition
The Facade Pattern is a structural design pattern that provides a simplified and unified interface to a set of interfaces in a subsystem. It defines a higher-level interface that makes the subsystem easier to use, thus promoting loose coupling between the client code and the system's components.

## Explanation in Simple Terms
Imagine you're at a coffee shop, and you want to order a cup of coffee. Instead of going into the intricate details of how coffee is brewed, you simply ask the barista for a "cappuccino." The barista, acting as a facade, takes care of the complex process, such as grinding the beans, frothing the milk, and brewing the espresso, and serves you with a delicious cappuccino. You don't need to understand the inner workings of the coffee machine; the barista provides a simplified interface.

In software, the Facade Pattern works in a similar way. It hides the complexities of a subsystem by providing a single, easy-to-use interface for the client code. This simplifies the client's interactions with the system and reduces dependencies.

## Code Related Explanation
### Usage Example:
```
public class CoffeeShop {
    public static void main(String[] args) {
        // Using the Facade pattern to order a cappuccino
        CoffeeMachineFacade coffeeMachine = new CoffeeMachineFacade();
        coffeeMachine.prepareCappuccino();
    }
}
```
