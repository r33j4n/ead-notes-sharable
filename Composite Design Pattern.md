

The Composite Design Pattern is a structural pattern that allows you to compose objects into tree structures to represent part-whole hierarchies. It lets clients treat individual objects and compositions of objects uniformly. This pattern is used when clients need to work with both individual objects and compositions of objects interchangeably.

**Key Components:**

1. **Component:**
   - Declares the interface for objects in the composition.
   - Implements default behavior common to all classes, including the leaf and composite classes.
   - Optionally, declares an interface for accessing and managing child components.

2. **Leaf:**
   - Represents individual objects in the composition.
   - Implements the behavior defined in the `Component` interface.

3. **Composite:**
   - Represents a composition of objects.
   - Contains child components, which can be either leaves or other composites.
   - Implements the behavior defined in the `Component` interface by delegating to its children.

**Example Code:**

Let's consider an example of a graphic system where we have simple shapes (leaf) and composite shapes (composed of multiple shapes).

```java
// Component interface
interface Graphic {
    void draw();
}

// Leaf class
class Ellipse implements Graphic {
    @Override
    public void draw() {
        System.out.println("Ellipse");
    }
}

// Leaf class
class Rectangle implements Graphic {
    @Override
    public void draw() {
        System.out.println("Rectangle");
    }
}

// Composite class
class CompositeGraphic implements Graphic {
    private List<Graphic> graphics = new ArrayList<>();

    public void addGraphic(Graphic graphic) {
        graphics.add(graphic);
    }

    @Override
    public void draw() {
        System.out.println("Composite Graphic:");
        for (Graphic graphic : graphics) {
            graphic.draw();
        }
    }
}

// Client code
public class CompositeClient {
    public static void main(String[] args) {
        // Create leaf shapes
        Ellipse ellipse = new Ellipse();
        Rectangle rectangle = new Rectangle();

        // Create a composite shape
        CompositeGraphic composite = new CompositeGraphic();
        composite.addGraphic(ellipse);
        composite.addGraphic(rectangle);

        // Draw individual shapes and the composite shape
        ellipse.draw();
        System.out.println();

        rectangle.draw();
        System.out.println();

        composite.draw();
    }
}
```

**Explanation:**

- The `Graphic` interface declares the common interface for leaf and composite classes.
- `Ellipse` and `Rectangle` are leaf classes implementing the `Graphic` interface.
- `CompositeGraphic` is a composite class that can contain other `Graphic` objects, either leaves or composites.
- The client code can work with individual shapes (leaves) or composite shapes seamlessly.

**Why it is Used:**

1. **Uniformity of Interface:**
   - **Explanation:** The Composite pattern provides a uniform interface for individual objects and compositions of objects. Clients can treat both types uniformly, simplifying the client code.
   - **Example:** In the provided example, both individual shapes and composite shapes implement the same `Graphic` interface, allowing them to be used interchangeably.

2. **Complex Object Structures:**
   - **Explanation:** This pattern is useful when you have complex object structures that can be represented as part-whole hierarchies. It allows you to work with these structures in a recursive manner.
   - **Example:** In a graphic system, a composite shape can contain other composite shapes and individual shapes, creating a hierarchical structure.

3. **Recursive Composition:**
   - **Explanation:** The Composite pattern supports recursive composition of objects. A composite can contain other composites, forming a tree structure.
   - **Example:** In the provided example, `CompositeGraphic` can contain other `Graphic` objects, allowing the creation of complex compositions.

4. **Simplifies Client Code:**
   - **Explanation:** Clients can work with individual objects and compositions using a common interface. This simplifies the client code and reduces the need for conditional statements to distinguish between leaf and composite objects.
   - **Example:** The client code in the provided example can draw individual shapes and composite shapes without knowing their specific types.

**Use Cases:**

1. **Graphic Systems:**
   - **Scenario:** In a graphic system, where simple shapes can be composed to create more complex shapes and hierarchies.
   - **Example:** Creating a scene with trees composed of branches and leaves, where each part can be a graphic object.

2. **Document Structures:**
   - **Scenario:** In a document editor, where a document can contain paragraphs, images, and tables, and each of these elements can further contain other elements.
   - **Example:** Representing a document structure with a composite pattern, where a document is a composite containing paragraphs, images, and tables.

3. **Organization Structures:**
   - **Scenario:** Representing organization structures where departments can contain sub-departments or employees, creating a hierarchical structure.
   - **Example:** Modeling an organization chart using a composite pattern, where an organization can contain departments, and departments can contain sub-departments or employees.

**Learning and Recall:**

- Understand the roles of `Component`, `Leaf`, and `Composite` in the pattern.
- Recognize how the pattern provides a uniform interface for individual objects and compositions.
- Visualize scenarios where the Composite pattern is beneficial, especially in dealing with part-whole hierarchies or structures that can be represented as trees.