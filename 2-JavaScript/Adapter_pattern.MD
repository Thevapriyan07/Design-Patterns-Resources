
# Adapter Pattern in JavaScript


## Definition
The Adapter Pattern is a design pattern in JavaScript used to make two incompatible interfaces work together. It allows objects with incompatible interfaces to collaborate by creating an adapter that serves as a bridge between them. This enables communication and cooperation between objects that wouldn't normally work together.

## Explanation in Simple Terms
Think of the Adapter Pattern as a plug adapter used when you travel to a foreign country. Your electronic device has one type of plug, and the wall socket in the foreign country has a different type of outlet. The adapter serves as a bridge between the two, allowing your device to connect to the foreign socket and function properly.

In JavaScript, the Adapter Pattern is like this plug adapter, allowing two objects with different interfaces to work together seamlessly. It translates the methods of one object into a format that the other object can understand, facilitating communication between them.


## Code Related Explanation

Here's an example of how you can implement the Adapter Pattern in JavaScript:

```bash
// Existing interface that we want to adapt
class OldSystem {
  request() {
    return 'Old System is processing the request.';
  }
}

// New and improved interface
class NewSystem {
  specificRequest() {
    return 'New System is processing the request.';
  }
}

// Adapter to make the OldSystem compatible with the NewSystem
class Adapter {
  constructor(oldSystem) {
    this.oldSystem = oldSystem;
  }

  specificRequest() {
    const response = this.oldSystem.request();
    return `Adapter converts the response: ${response}`;
  }
}

// Example usage
const oldSystem = new OldSystem();
const newSystem = new NewSystem();

const adapter = new Adapter(oldSystem);

console.log(oldSystem.request()); // Outputs: Old System is processing the request.
console.log(newSystem.specificRequest()); // Outputs: New System is processing the request.

// The Adapter allows the OldSystem to work with the NewSystem
console.log(adapter.specificRequest()); // Outputs: Adapter converts the response: Old System is processing the request.
```
In this code:

- 'OldSystem' represents an existing interface with a method request.
- 'NewSystem' is the improved interface with a method specificRequest.
- The 'Adapter' class is responsible for adapting the OldSystem to work with the 'NewSystem'. It takes an instance of OldSystem and translates its method call into a format compatible with the NewSystem.
- When you use the Adapter, it allows the old system to work with the new system without changing the old system's code.

The Adapter Pattern is useful when you want to integrate new functionality or systems without modifying existing code, making it a valuable tool for code reusability and compatibility.

