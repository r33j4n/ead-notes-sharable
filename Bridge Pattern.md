**Bridge Design Pattern - Simple Example:**

Let's consider a simple example of a Bridge pattern involving shapes and drawing implementations. We'll have different shapes (abstraction) and different ways to draw them (implementation). The Bridge pattern allows us to independently change or extend shapes and drawing implementations.

```java
// Implementor interface
interface DrawingAPI {
    void drawCircle(int x, int y, int radius);
}

// Concrete Implementor 1
class DrawingAPI1 implements DrawingAPI {
    @Override
    public void drawCircle(int x, int y, int radius) {
        System.out.printf("API1 - Drawing Circle at (%d, %d) with radius %d%n", x, y, radius);
    }
}

// Concrete Implementor 2
class DrawingAPI2 implements DrawingAPI {
    @Override
    public void drawCircle(int x, int y, int radius) {
        System.out.printf("API2 - Drawing Circle at (%d, %d) with radius %d%n", x, y, radius);
    }
}

// Abstraction
abstract class Shape {
    protected DrawingAPI drawingAPI;

    protected Shape(DrawingAPI drawingAPI) {
        this.drawingAPI = drawingAPI;
    }

    public abstract void draw();
}

// Refined Abstraction
class Circle extends Shape {
    private int x, y, radius;

    public Circle(int x, int y, int radius, DrawingAPI drawingAPI) {
        super(drawingAPI);
        this.x = x;
        this.y = y;
        this.radius = radius;
    }

    @Override
    public void draw() {
        drawingAPI.drawCircle(x, y, radius);
    }
}

// Client code
public class BridgeSimpleExample {
    public static void main(String[] args) {
        DrawingAPI api1 = new DrawingAPI1();
        DrawingAPI api2 = new DrawingAPI2();

        // Create circles with different drawing implementations
        Shape circle1 = new Circle(1, 2, 3, api1);
        Shape circle2 = new Circle(5, 7, 11, api2);

        // Draw circles
        circle1.draw();
        circle2.draw();
    }
}
```

**Explanation:**

- `DrawingAPI` is the interface that defines the methods for drawing circles.
- `DrawingAPI1` and `DrawingAPI2` are concrete implementations of the `DrawingAPI` interface.
- `Shape` is the abstraction, and `Circle` is a refined abstraction. They both have a reference to a `DrawingAPI` object.
- The client code can create different shapes and associate them with different drawing APIs.

**How it Works:**

1. `DrawingAPI` provides the interface for drawing circles.
2. `DrawingAPI1` and `DrawingAPI2` are concrete implementations of `DrawingAPI`.
3. `Shape` is the abstraction that maintains a reference to a `DrawingAPI` object.
4. `Circle` is a specific shape that extends `Shape` and delegates its drawing to the associated `DrawingAPI`.

**Why it is Used:**

- **Decoupling Abstraction and Implementation:** Allows the abstraction and implementation to vary independently.
- **Open/Closed Principle:** The pattern makes it easy to add new abstractions or implementations without modifying the existing code.

**Use Cases:**

1. **GUI Frameworks:**
   - Abstraction: Different UI components (buttons, windows).
   - Implementor: Drawing methods for different platforms.

2. **Remote Controls:**
   - Abstraction: Different remote control devices (buttons, functions).
   - Implementor: Commands for different electronic devices.

**Learning and Recall:**

- Understand the concept of abstraction and implementation separation.
- Recognize the roles of Abstraction, Refined Abstraction, Implementor, and Concrete Implementor in the pattern.
- Visualize scenarios where changes in the abstraction or implementation should not affect each other, making the Bridge pattern beneficial.