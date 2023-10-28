# Mediator Design Pattern in Java

## Definition
The Mediator Design Pattern is a behavioral pattern that promotes loose coupling between objects by encapsulating their interaction within a mediator object. It is used to reduce the direct communication between objects and instead, they communicate through a central mediator. This pattern helps in managing complex communication and interactions between multiple objects by centralizing control.

## Explanation in Simple Terms
Imagine you have a chat application where multiple users can send messages to each other. Without the Mediator pattern, each user would need to know the details of every other user and their messages. This would lead to a tightly coupled and complex mess of code. With the Mediator pattern, there's a central chat room (mediator) where users send their messages. The mediator then handles the distribution of messages to the right recipients, making communication more organized and less dependent on the knowledge of other users.

## Code-Related Explanation
In this Java repository, we have implemented the Mediator pattern to illustrate how it works. We have the following key components:

- `Mediator`: This interface defines the contract for the mediator, which includes methods for registering participants (users) and sending messages.

- `ConcreteMediator`: This class implements the `Mediator` interface. It manages the participants (users) and ensures that messages are forwarded to the correct recipient.

- `User`: This class represents the participants in the system. Users can send messages to the mediator, and the mediator will ensure the message is sent to the right recipient.

- `Main`: This is the entry point of the program. It demonstrates how users can communicate through the mediator.

### Sample Usage:

```java
public class Main {
    public static void main(String[] args) {
        ConcreteMediator chatRoom = new ConcreteMediator();

        User alice = new User("Alice", chatRoom);
        User bob = new User("Bob", chatRoom);

        alice.sendMessage("Hello, Bob!");
        bob.sendMessage("Hi, Alice!");

        // The mediator ensures that the messages are delivered to the right recipient.
    }
}
