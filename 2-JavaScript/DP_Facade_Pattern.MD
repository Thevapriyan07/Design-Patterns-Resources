# Design Pattern: Facade Pattern in JavaScript

## Definition

The Facade Pattern is a structural design pattern that simplifies the interface to a set of interfaces in a subsystem. It acts as a high-level interface that makes it easier to use and understand a complex system by providing a unified and simplified API.

## Explanation in Simple Terms

Consider a scenario where you're interacting with a complex system, like starting a car. Rather than manually engaging with each component (ignition, fuel injection, etc.), the car provides a simplified interface—the ignition key. Turning the key is like using a facade; it abstracts away the complexity of starting the car.

In software, the Facade Pattern works similarly. It presents a simplified interface to a more complex set of classes, making it easier for clients to use the system without dealing with its intricate details.

## Code Related Explanation

### Before Using Facade Pattern
javascript
class Engine {
  start() {
    console.log('Engine started');
  }
}

class FuelInjector {
  inject() {
    console.log('Fuel injected');
  }
}

class Ignition {
  ignite() {
    console.log('Ignition engaged');
  }
}

### Using Facade Pattern

javascript
class CarFacade {
  constructor() {
    this.engine = new Engine();
    this.fuelInjector = new FuelInjector();
    this.ignition = new Ignition();
  }

  start() {
    this.engine.start();
    this.fuelInjector.inject();
    this.ignition.ignite();
  }
}


