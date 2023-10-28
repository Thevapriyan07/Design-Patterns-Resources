# Design Pattern: Decorator

## Table of Contents
- [Definition](#definition)
- [Explanation in Simple Terms](#explanation-in-simple-terms)
- [Code-Related Explanation](#code-related-explanation)

## Definition
The Decorator pattern is a structural design pattern that allows behavior to be added to individual objects, either statically or dynamically, without affecting the behavior of other objects from the same class. It is achieved by creating a set of decorator classes that are used to wrap concrete components. Decorators provide a flexible alternative to subclassing for extending functionality.

## Explanation in Simple Terms
Think of the Decorator pattern like adding layers to an object. Each layer (decorator) can add new features or modifications to the base object without changing its core identity. It's like decorating a cake with different toppings. You have a plain cake (the base object), and you can add chocolate frosting, sprinkles, or other decorations (decorators) as needed.

For example, in a text editor, you might have a basic text editing component. With decorators, you can dynamically add features like spell checking, bold text, or italics to the text without changing the core text editing functionality. This keeps your code modular and easy to extend.

## Code-Related Explanation
In Java, the Decorator pattern is implemented by creating a common interface or an abstract class (the component) that represents the base object. Concrete components implement this interface. Decorator classes also implement the same interface and contain a reference to the component. They add their own behavior and delegate to the component when needed.

Here's a basic code structure for the Decorator pattern in Java:

```java
// Common interface for components
interface Text {
    String getContent();
}

// Concrete component
class PlainText implements Text {
    private String content;

    public PlainText(String content) {
        this.content = content;
    }

    public String getContent() {
        return content;
    }
}

// Decorator
abstract class TextDecorator implements Text {
    protected Text text;

    public TextDecorator(Text text) {
        this.text = text;
    }

    public String getContent() {
        return text.getContent();
    }
}

// Concrete decorators
class BoldDecorator extends TextDecorator {
    public BoldDecorator(Text text) {
        super(text);
    }

    public String getContent() {
        return "<b>" + super.getContent() + "</b>";
    }
}

class ItalicDecorator extends TextDecorator {
    public ItalicDecorator(Text text) {
        super(text);
    }

    public String getContent() {
        return "<i>" + super.getContent() + "</i>";
    }
}
