# DP Bridge Pattern in Java

## Definition
The Bridge Pattern is a structural design pattern that separates an object’s abstraction from its implementation so that the two can vary independently. This pattern involves creating a bridge interface that acts as a connector, allowing the abstraction and implementation to vary without affecting each other.

## Explanation in Simple Terms
Imagine you have different shapes and rendering devices. The Bridge Pattern helps you draw these shapes on various devices without modifying the shape classes or rendering classes every time a new combination is needed. Instead, you create a bridge between shapes and renderers, allowing them to change independently. It's like building a bridge between two islands, where the islands represent shapes and renderers, and the bridge connects them without changing the islands themselves.

## Code Related Explanation
In this repository, we provide a Java implementation of the Bridge Pattern. We have the following main components:

- `Shape` and its subclasses (e.g., `Circle`, `Square`): These represent the abstraction part and define the methods for the shape.
- `Renderer` and its subclasses (e.g., `VectorRenderer`, `RasterRenderer`): These represent the implementation part and define the rendering logic.
- `ShapeRendererBridge` interface: This acts as the bridge connecting the abstraction (Shape) and implementation (Renderer).
- `Main` class: It demonstrates how different shapes can be drawn on different rendering devices by utilizing the Bridge Pattern.

### Example Usage
```java
public class Main {
    public static void main(String[] args) {
        Renderer vectorRenderer = new VectorRenderer();
        Renderer rasterRenderer = new RasterRenderer();

        Shape circle = new Circle(vectorRenderer);
        Shape square = new Square(rasterRenderer);

        circle.draw();
        square.draw();
    }
}
