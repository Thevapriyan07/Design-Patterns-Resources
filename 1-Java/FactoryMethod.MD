
# Factory Method Pattern in Java



## Definition
The Factory Method is a design pattern in Java that falls under the category of creational design patterns. It provides an interface for creating objects, but the specific classes that will be instantiated are determined by the subclasses. This pattern promotes loose coupling between the creator and the product, allowing for flexibility and extensibility in object creation.

## Explanation in Simple Terms
Think of the Factory Method pattern as a magic factory that creates different types of objects based on your request. Imagine you need to build different types of vehicles, like cars, bicycles, and motorcycles. Instead of directly creating these vehicles in your code, you ask the factory to create the specific type you need. The factory handles the details of creating the right vehicle, making it easier to change or add new vehicle types without affecting the rest of your code.

This pattern is particularly useful when you have a family of related classes (e.g., different types of vehicles) and you want to delegate the responsibility of object creation to subclasses.


## Code Related Explanation

Here's an example of how you can implement the Factory Method pattern in Java:

```bash
// Product interface
interface Vehicle {
    void start();
}

// Concrete products
class Car implements Vehicle {
    public void start() {
        System.out.println("Car started.");
    }
}

class Bicycle implements Vehicle {
    public void start() {
        System.out.println("Bicycle started.");
    }
}

// Creator interface
interface VehicleFactory {
    Vehicle createVehicle();
}

// Concrete creators
class CarFactory implements VehicleFactory {
    public Vehicle createVehicle() {
        return new Car();
    }
}

class BicycleFactory implements VehicleFactory {
    public Vehicle createVehicle() {
        return new Bicycle();
    }
}

public class Main {
    public static void main(String[] args) {
        VehicleFactory factory1 = new CarFactory();
        Vehicle car = factory1.createVehicle();
        car.start();  // Outputs "Car started."

        VehicleFactory factory2 = new BicycleFactory();
        Vehicle bicycle = factory2.createVehicle();
        bicycle.start();  // Outputs "Bicycle started."
    }
}

```
In this code:

- We have a Vehicle interface that represents the product, and two concrete product classes, Car and Bicycle, implementing it.
- The VehicleFactory interface defines the factory method, createVehicle(), which is responsible for creating the product.
- Two concrete creator classes, CarFactory and BicycleFactory, implement the factory method to create specific instances of vehicles.
- In the Main class, we create instances of the factories and use them to create and start vehicles.

This structure allows you to extend the pattern easily by adding new product types and corresponding factories, promoting flexibility in your codebase.

