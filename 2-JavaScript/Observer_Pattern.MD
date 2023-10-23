# Observer Pattern in JavaScript
## Definition
The Observer Pattern is a behavioral design pattern where an object, known as the subject, maintains a list of dependents, called observers, that are notified of any state changes, typically by calling one of their methods. This pattern is used to define a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.

## Explanation in Simple Terms
Imagine you have a group of friends who are interested in updates about your life. The Observer Pattern is like having a notification system for your life events. Whenever something significant happens (you change your job, move to a new city, etc.), your friends (observers) get notified automatically without you having to individually inform each of them. In programming, the Observer Pattern works similarly, allowing objects to subscribe to changes in another object and get notified automatically.

## Code Related Explanation
### Implementation
To implement the Observer Pattern in JavaScript, you typically have a subject that maintains a list of observers. Observers register themselves with the subject, and when the subject's state changes, it notifies all registered observers.
class Observable {
  constructor() {
    this.observers = [];
  }

  addObserver(observer) {
    this.observers.push(observer);
  }

  removeObserver(observer) {
    this.observers = this.observers.filter(obs => obs !== observer);
  }

  notifyObservers() {
    this.observers.forEach(observer => observer.update());
  }
}
