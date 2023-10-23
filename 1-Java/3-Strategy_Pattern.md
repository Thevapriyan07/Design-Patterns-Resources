# Strategy Pattern in Java

## Definition:

The Strategy Pattern is a behavioral design pattern in Java. It defines a family of algorithms, encapsulates each one of them, and makes them interchangeable. This pattern allows you to select an algorithm or behavior at runtime, without altering the code that uses these behaviors. It's particularly useful when you have multiple ways to perform a specific task and want to choose the most suitable one dynamically.

## Explanation in Simple Terms:

Think of the Strategy Pattern as a toolkit with different tools for the same job. You have a problem to solve, and you can choose the best tool from your toolkit to get the job done. You can switch tools whenever needed, and your problem-solving process remains flexible. It's like changing the weapon you use in a video game - you pick the one that suits the situation.

In the context of Java, you create a set of interchangeable algorithms (strategies) and use them as needed, making your code more adaptable and maintainable.

## Code-Related Explanation:

The Strategy Pattern is typically implemented as follows in Java:

1. Define an interface (or an abstract class) that declares the method(s) to be used by different strategies.
2. Create concrete classes that implement this interface and provide their own implementations of the method(s).
3. In a context class, include a reference to the interface and a method to set the concrete strategy.
4. The client code can create a context object and set the strategy to use.

Here's a simple code example:

```java
// Step 1: Define a strategy interface
interface PaymentStrategy {
    void pay(int amount);
}

// Step 2: Create concrete strategy classes
class CreditCardPayment implements PaymentStrategy {
    private String cardNumber;
    private String name;

    public CreditCardPayment(String cardNumber, String name) {
        this.cardNumber = cardNumber;
        this.name = name;
    }

    @Override
    public void pay(int amount) {
        System.out.println(amount + " paid with credit card: " + cardNumber);
    }
}

class PayPalPayment implements PaymentStrategy {
    private String email;

    public PayPalPayment(String email) {
        this.email = email;
    }

    @Override
    public void pay(int amount) {
        System.out.println(amount + " paid with PayPal using email: " + email);
    }
}

// Step 3: Create a context class
class ShoppingCart {
    private PaymentStrategy paymentStrategy;

    public void setPaymentStrategy(PaymentStrategy paymentStrategy) {
        this.paymentStrategy = paymentStrategy;
    }

    public void checkout(int amount) {
        paymentStrategy.pay(amount);
    }
}

// Step 4: Client code
public class Main {
    public static void main(String[] args) {
        ShoppingCart cart = new ShoppingCart();

        // Select a payment strategy dynamically
        PaymentStrategy creditCard = new CreditCardPayment("1234-5678-9876-5432", "John Doe");
        PaymentStrategy paypal = new PayPalPayment("john.doe@example.com");

        // Use the selected strategy for payment
        cart.setPaymentStrategy(creditCard);
        cart.checkout(100);

        cart.setPaymentStrategy(paypal);
        cart.checkout(50);
    }
}
```

In this example:

- The `PaymentStrategy` interface declares the method `pay`, which is implemented by concrete strategies.
- The `ShoppingCart` class contains a reference to the current payment strategy, and you can switch payment methods dynamically.

The Strategy Pattern helps keep the code clean and allows you to add or change strategies without altering the client code.
