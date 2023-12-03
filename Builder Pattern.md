**Builder Design Pattern:**
- **Definition:** The Builder Design Pattern is a creational pattern that separates the construction of a complex object from its representation, allowing the same construction process to create different representations. It involves a Director class, a Builder interface, and ConcreteBuilder classes.

- **Key Components:**
  1. **Builder:** Declares an interface for constructing parts of the product.
  2. **ConcreteBuilder:** Implements the Builder interface and constructs the actual product.
  3. **Product:** Represents the complex object being constructed.
  4. **Director:** Manages the construction process by directing the ConcreteBuilder.

- **Example Code in Java:**
  ```java
  // Product
  class Computer {
      private String cpu;
      private String memory;
      private String storage;

      public void setCpu(String cpu) {
          this.cpu = cpu;
      }

      public void setMemory(String memory) {
          this.memory = memory;
      }

      public void setStorage(String storage) {
          this.storage = storage;
      }

      public void display() {
          System.out.println("Computer Configuration:\nCPU: " + cpu + "\nMemory: " + memory + "\nStorage: " + storage);
      }
  }

  // Builder Interface
  interface ComputerBuilder {
      void buildCpu();
      void buildMemory();
      void buildStorage();
      Computer getResult();
  }

  // ConcreteBuilder for Gaming Computer
  class GamingComputerBuilder implements ComputerBuilder {
      private Computer computer = new Computer();

      @Override
      public void buildCpu() {
          computer.setCpu("High-end Gaming CPU");
      }

      @Override
      public void buildMemory() {
          computer.setMemory("32GB RAM");
      }

      @Override
      public void buildStorage() {
          computer.setStorage("1TB SSD");
      }

      @Override
      public Computer getResult() {
          return computer;
      }
  }

  // ConcreteBuilder for Office Computer
  class OfficeComputerBuilder implements ComputerBuilder {
      private Computer computer = new Computer();

      @Override
      public void buildCpu() {
          computer.setCpu("Standard Office CPU");
      }

      @Override
      public void buildMemory() {
          computer.setMemory("8GB RAM");
      }

      @Override
      public void buildStorage() {
          computer.setStorage("500GB HDD");
      }

      @Override
      public Computer getResult() {
          return computer;
      }
  }

  // Director
  class ComputerDirector {
      private ComputerBuilder computerBuilder;

      public ComputerDirector(ComputerBuilder computerBuilder) {
          this.computerBuilder = computerBuilder;
      }

      public void constructComputer() {
          computerBuilder.buildCpu();
          computerBuilder.buildMemory();
          computerBuilder.buildStorage();
      }

      public Computer getConstructedComputer() {
          return computerBuilder.getResult();
      }
  }

  // Client Code
  public class BuilderClient {
      public static void main(String[] args) {
          ComputerBuilder gamingComputerBuilder = new GamingComputerBuilder();
          ComputerDirector gamingComputerDirector = new ComputerDirector(gamingComputerBuilder);

          gamingComputerDirector.constructComputer();
          Computer gamingComputer = gamingComputerDirector.getConstructedComputer();
          gamingComputer.display();

          System.out.println();

          ComputerBuilder officeComputerBuilder = new OfficeComputerBuilder();
          ComputerDirector officeComputerDirector = new ComputerDirector(officeComputerBuilder);

          officeComputerDirector.constructComputer();
          Computer officeComputer = officeComputerDirector.getConstructedComputer();
          officeComputer.display();
      }
  }
  ```

- **Why it is used:**
  - **Complex Object Construction:** It is used when an object has a complex construction process involving multiple steps, and the construction steps need to be abstracted from the client.
  - **Variety of Representations:** It allows the same construction process to create different representations of the product.

- **Use Cases:**
  1. **Building Different Types of Meals:**
     - **Example:** Constructing different types of meals (e.g., vegetarian, non-vegetarian) with various components (e.g., main course, side dishes, drinks).
     - **Code:**
       ```java
       // Product
       class Meal {
           private String mainCourse;
           private String sideDish;
           private String drink;

           // Setters and Display method
       }

       // Builder Interface
       interface MealBuilder {
           void buildMainCourse();
           void buildSideDish();
           void buildDrink();
           Meal getResult();
       }

       // ConcreteBuilder for Vegetarian Meal
       class VegetarianMealBuilder implements MealBuilder {
           private Meal meal = new Meal();

           @Override
           public void buildMainCourse() {
               meal.setMainCourse("Vegetarian Main Course");
           }

           @Override
           public void buildSideDish() {
               meal.setSideDish("Vegetarian Side Dish");
           }

           @Override
           public void buildDrink() {
               meal.setDrink("Water");
           }

           @Override
           public Meal getResult() {
               return meal;
           }
       }

       // ConcreteBuilder for Non-Vegetarian Meal
       class NonVegetarianMealBuilder implements MealBuilder {
           // Similar implementation as VegetarianMealBuilder with non-vegetarian components
       }

       // Director
       class MealDirector {
           private MealBuilder mealBuilder;

           public MealDirector(MealBuilder mealBuilder) {
               this.mealBuilder = mealBuilder;
           }

           public void constructMeal() {
               mealBuilder.buildMainCourse();
               mealBuilder.buildSideDish();
               mealBuilder.buildDrink();
           }

           public Meal getConstructedMeal() {
               return mealBuilder.getResult();
           }
       }

       // Client Code
       public class MealClient {
           public static void main(String[] args) {
               MealBuilder vegetarianMealBuilder = new VegetarianMealBuilder();
               MealDirector vegetarianMealDirector = new MealDirector(vegetarianMealBuilder);

               vegetarianMealDirector.constructMeal();
               Meal vegetarianMeal = vegetarianMealDirector.getConstructedMeal();
               vegetarianMeal.display();

               System.out.println();

               MealBuilder nonVegetarianMealBuilder = new NonVegetarianMealBuilder();
               MealDirector nonVegetarianMealDirector = new MealDirector(nonVegetarianMealBuilder);

               nonVegetarianMealDirector.constructMeal();
               Meal nonVegetarianMeal = nonVegetarianMealDirector.getConstructedMeal();
               nonVegetarianMeal.display();
           }
       }
       ```

  2. **Document Building in a Word Processor:**
     - **Example:** Constructing different types of documents (e.g., letter, report) with various components (e.g., header, body, footer) in a word processor.
     - **Code:**
       ```java
       // Product
       class Document {
           private String header;
           private String body;
           private String footer;

           // Setters and Display method
       }

       // Builder Interface
       interface DocumentBuilder {
           void buildHeader();
           void buildBody();
           void buildFooter();
           Document getResult();
       }

       // ConcreteBuilder for Letter Document
       class LetterDocumentBuilder implements DocumentBuilder {
           private Document document = new Document();

           @Override
           public void buildHeader() {
               document.setHeader("Letter Header");
           }

           @Override
           public void buildBody() {
               document.setBody("Dear recipient,\n\nThis is a letter body.");
          

 }

           @Override
           public void buildFooter() {
               document.setFooter("Sincerely,\nSender");
           }

           @Override
           public Document getResult() {
               return document;
           }
       }

       // ConcreteBuilder for Report Document
       class ReportDocumentBuilder implements DocumentBuilder {
           // Similar implementation as LetterDocumentBuilder with report components
       }

       // Director
       class DocumentDirector {
           private DocumentBuilder documentBuilder;

           public DocumentDirector(DocumentBuilder documentBuilder) {
               this.documentBuilder = documentBuilder;
           }

           public void constructDocument() {
               documentBuilder.buildHeader();
               documentBuilder.buildBody();
               documentBuilder.buildFooter();
           }

           public Document getConstructedDocument() {
               return documentBuilder.getResult();
           }
       }

       // Client Code
       public class DocumentClient {
           public static void main(String[] args) {
               DocumentBuilder letterDocumentBuilder = new LetterDocumentBuilder();
               DocumentDirector letterDocumentDirector = new DocumentDirector(letterDocumentBuilder);

               letterDocumentDirector.constructDocument();
               Document letterDocument = letterDocumentDirector.getConstructedDocument();
               letterDocument.display();

               System.out.println();

               DocumentBuilder reportDocumentBuilder = new ReportDocumentBuilder();
               DocumentDirector reportDocumentDirector = new DocumentDirector(reportDocumentBuilder);

               reportDocumentDirector.constructDocument();
               Document reportDocument = reportDocumentDirector.getConstructedDocument();
               reportDocument.display();
           }
       }
       ```

- **Learning and Recall:**
  - **Understand the Separation of Concerns:**
    - Recognize how the Builder pattern separates the construction of a complex object from its representation.
  - **Examples for Recall:**
    - Visualize scenarios where complex objects with multiple components need to be constructed step by step, and the Builder pattern simplifies this process.
    - Consider situations where the same construction steps can be used to create different representations of the product.