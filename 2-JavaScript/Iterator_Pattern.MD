# Iterator Pattern in JavaScript

## Definition

The Iterator Pattern is a behavioral design pattern that provides a way to access elements of an aggregate object sequentially without exposing its underlying representation. It separates the traversal of an object from its structure, making it possible to iterate over different types of collections in a consistent manner.

## Explanation in Simple Terms

Imagine you have a collection of items, such as an array or a list of data, and you want to go through each item one by one. The Iterator Pattern allows you to do this in a clean and organized way. It abstracts the process of iterating over the collection so that you don't have to worry about the underlying structure of the collection. You can simply ask for the next item, and it will be provided, regardless of whether the collection is an array, a linked list, or any other data structure.

## Code Related Explanation

In this repository, you will find JavaScript code examples that demonstrate the implementation of the Iterator Pattern. The code includes an iterator object that allows you to iterate over a simple collection. It provides methods like next(), hasNext(), and an example of how to use it.

### Usage Example

```javascript
const collection = [1, 2, 3, 4, 5];
const iterator = createIterator(collection);

while (iterator.hasNext()) {
  console.log(iterator.next());
}
