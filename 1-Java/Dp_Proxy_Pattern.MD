# DP Proxy Pattern in Java

## Definition
The Proxy Pattern is a structural design pattern that provides an object representing another object. It acts as a surrogate or placeholder for another object to control access to it.

## Explanation in Simple Terms
Imagine you have an expensive or resource-intensive object that you want to use in your application. You don't want to create this object until you really need it, to save resources. The Proxy Pattern allows you to create a "proxy" object that stands in for the real object. This proxy object controls access to the real object and ensures that it's only created or accessed when necessary. It's like having a personal assistant who fetches your coffee only when you ask for it, rather than having it prepared in advance.

In simpler terms, the Proxy Pattern is like having a middleman that manages your interactions with the real object. This middleman can handle tasks like lazy initialization, access control, and logging.

## Code Related Explanation
To implement the Proxy Pattern in Java, you can follow these steps:

### Create an Interface: 
Define an interface that both the real object and proxy will implement. This interface contains the methods that the proxy and real object should provide.
```
public interface Image {
    void display();
}
```
### Create a Real Object:
Implement the interface with a class that represents the real object you want to control access to. This class should contain the actual business logic.
```
public class RealImage implements Image {
    private String filename;

    public RealImage(String filename) {
        this.filename = filename;
        loadFromDisk();
    }

    private void loadFromDisk() {
        System.out.println("Loading " + filename);
    }

    public void display() {
        System.out.println("Displaying " + filename);
    }
}
```
### Create a Proxy Object: 
Implement a proxy class that also implements the interface. The proxy class should have a reference to the real object but only create or access it when needed.
```
public class ProxyImage implements Image {
    private RealImage realImage;
    private String filename;

    public ProxyImage(String filename) {
        this.filename = filename;
    }

    public void display() {
        if (realImage == null) {
            realImage = new RealImage(filename);
        }
        realImage.display();
    }
}
```
### Client Code:
Finally, you can use the proxy to control access to the real object.
```
public class Client {
    public static void main(String[] args) {
        Image image = new ProxyImage("example.jpg");

        // The real image is loaded and displayed only when needed.
        image.display();
    }
}
```
