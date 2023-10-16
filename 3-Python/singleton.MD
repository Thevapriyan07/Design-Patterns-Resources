# Design Pattern: Singleton in Python

## Definition

A Singleton is a design pattern in software engineering that ensures a class has only one instance and provides a global point of access to that instance. It is commonly used when you want to limit the creation of objects to only one instance, making it useful in scenarios where exactly one object is needed to coordinate actions across the system.


## Explanation

Imagine you have a special container, and you want to make sure there's only one of these containers in your whole house. The Singleton pattern is like a guard that watches over this container. It makes sure there's only one of them, and if you need to use it, you can always find it easily.

In software, this is useful when you want to manage something unique, like a database connection or settings for your app. It stops you from creating multiple copies of the same thing, which can cause problems.


## Code Explanation

To create a Singleton in Python, you can use a class with a private instance variable and a method to access it.

```py
class Singleton:
    _instance = None

    def __new__(cls):
        if cls._instance is None:
            cls._instance = super(Singleton, cls).__new__(cls)
            cls._instance.initialize()
        return cls._instance

    def initialize(self):
        self.some_data = "Initialized data"


# create a Singleton object
singleton1 = Singleton()
singleton2 = Singleton()

# Both 'singleton1' and 'singleton2' point to the same instance

# Outputs: "Initialized data"
print(singleton1.some_data)

# Outputs: "Initialized data"
print(singleton2.some_data)
```

In this code, the `__new__` method ensures that there's only **one** instance of the Singleton class. When you create multiple objects, they all point to the same instance. The `initialize` method allows you to perform optional initialization when the instance is first created.
