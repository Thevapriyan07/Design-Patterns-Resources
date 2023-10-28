# Strategy Design Pattern in Java
## Definition
The Strategy Pattern is a behavioral design pattern that defines a family of algorithms, encapsulates each one of them, and makes them interchangeable. It allows a client to choose the appropriate algorithm to use at runtime. This pattern promotes decoupling between the client and the specific implementation of an algorithm.

## Explanation in Simple Terms
Imagine you have a computer game, and you want to add a feature that allows the player character to perform different types of attacks. The Strategy pattern lets you define various attack strategies (e.g., sword attack, magic attack, ranged attack) and dynamically switch between them during gameplay. It's like having multiple strategies in your arsenal and choosing the most effective one for a given situation without changing the game's core logic.

## Code-Related Explanation
In Java, you can implement the Strategy pattern with the following components:

Strategy Interface: Define an interface that represents the strategy's methods. In our example, it could be an AttackStrategy interface with a method like performAttack().
```
public interface AttackStrategy {
    void performAttack();
}
public class PlayerCharacter {
    private AttackStrategy attackStrategy;

    public void setAttackStrategy(AttackStrategy attackStrategy) {
        this.attackStrategy = attackStrategy;
    }

    public void performAttack() {
        attackStrategy.performAttack();
    }
}
PlayerCharacter player = new PlayerCharacter();
player.setAttackStrategy(new SwordAttack());
player.performAttack(); // Outputs: Performing a sword attack!

player.setAttackStrategy(new MagicAttack());
player.performAttack(); // Outputs: Casting a magic spell!
```
