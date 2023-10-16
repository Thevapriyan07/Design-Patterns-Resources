# Design Patterns Adapter in Python

## Table of Contents

- [Definition](#definition)
- [How Adapter Pattern Works](#How-Adapter-Pattern-Works)
- [Code Related Explanation](#code-related-explanation)

## Definition

The Adapter pattern is a structural design pattern that allows objects with incompatible interfaces to work together by creating a bridge between them. It enables objects to collaborate without needing to modify their existing code.

## How Adapter Pattern Works

In Python, the Adapter pattern involves creating a new class (the adapter) that wraps an existing class (the adaptee) and provides a compatible interface that other parts of the code can use.

The adapter class acts as an intermediary, translating the methods and functionalities of the adaptee class into a format that is expected by the client code. It allows the client code to interact with the adaptee class through a common interface provided by the adapter.

## Code-related-explanation

``` Python
# Adaptee class with an incompatible interface
class Adaptee:
    def specific_method(self):
        print("Specific method from Adaptee")

# Target interface expected by the client code
class Target:
    def expected_method(self):
        pass

# Adapter class that adapts Adaptee to the Target interface
class Adapter(Target):
    def __init__(self, adaptee):
        self.adaptee = adaptee

    def expected_method(self):
        self.adaptee.specific_method()

# Client code that expects the Target interface
def client_code(target):
    target.expected_method()

# Usage
adaptee = Adaptee()
adapter = Adapter(adaptee)
client_code(adapter)  # Output: "Specific method from Adaptee"

```

In the example above, Adaptee is an existing class with an incompatible interface. Target is the target interface that the client code expects. The Adapter class wraps the Adaptee class and provides the expected_method() that conforms to the Target interface.

The client code interacts with the Adapter class, which internally delegates the call to the Adaptee class, translating the method call from the Target interface to the specific method of the Adaptee class.

By using the Adapter pattern, you can integrate existing classes with incompatible interfaces into your codebase without needing to modify their implementation. The adapter acts as a bridge, allowing different objects to collaborate seamlessly.
