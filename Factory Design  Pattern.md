

- **Definition:** The Factory Design Pattern is a creational pattern that provides an interface for creating instances of a class, but allows subclasses to alter the type of objects that will be created.
```java
// Product Interface
interface Product {
    void display();
}

// Concrete Product A
class ConcreteProductA implements Product {
    @Override
    public void display() {
        System.out.println("Concrete Product A");
    }
}

// Concrete Product B
class ConcreteProductB implements Product {
    @Override
    public void display() {
        System.out.println("Concrete Product B");
    }
}

// Factory Interface
interface Factory {
    Product createProduct();
}

// Concrete Factory A
class ConcreteFactoryA implements Factory {
    @Override
    public Product createProduct() {
        return new ConcreteProductA();
    }
}

// Concrete Factory B
class ConcreteFactoryB implements Factory {
    @Override
    public Product createProduct() {
        return new ConcreteProductB();
    }
}

// Client Code
public class Client {
    public static void main(String[] args) {
        Factory factoryA = new ConcreteFactoryA();
        Product productA = factoryA.createProduct();
        productA.display();

        Factory factoryB = new ConcreteFactoryB();
        Product productB = factoryB.createProduct();
        productB.display();
    }
}

```

- **Why it is used:**
    
    - **Abstraction of Object Creation:** It allows the client code to create objects without specifying their exact class, promoting loose coupling.
    - **Flexibility:** Easily swap between different implementations of products without changing the client code.
    - **Encapsulation:** It encapsulates the object creation logic, making it easier to manage and extend.
- **Use Cases:**
    
    1. **Database Connection Factory:**
        
        - **Example:** Different databases (MySQL, PostgreSQL) can have their own concrete factories for creating database connections.
        - **Code:**
            
            
            ```java
            // Database Connection Interface
interface DatabaseConnection {
    void connect();
}

// MySQL Connection
class MySqlConnection implements DatabaseConnection {
    @Override
    public void connect() {
        System.out.println("Connected to MySQL Database");
    }
}

// PostgreSQL Connection
class PostgreSqlConnection implements DatabaseConnection {
    @Override
    public void connect() {
        System.out.println("Connected to PostgreSQL Database");
    }
}

// Database Connection Factory
interface DatabaseConnectionFactory {
    DatabaseConnection createConnection();
}

// MySQL Connection Factory
class MySqlConnectionFactory implements DatabaseConnectionFactory {
    @Override
    public DatabaseConnection createConnection() {
        return new MySqlConnection();
    }
}

// PostgreSQL Connection Factory
class PostgreSqlConnectionFactory implements DatabaseConnectionFactory {
    @Override
    public DatabaseConnection createConnection() {
        return new PostgreSqlConnection();
    }
}

// Client Code
public class DatabaseClient {
    public static void main(String[] args) {
        DatabaseConnectionFactory factory = new MySqlConnectionFactory();
        DatabaseConnection connection = factory.createConnection();
        connection.connect();
    }
}

```

**Logger Factory:**

- **Example:** Different logging mechanisms (FileLogger, ConsoleLogger) can be created using the factory pattern.
```java
// Logger Interface
interface Logger {
    void log(String message);
}

// File Logger
class FileLogger implements Logger {
    @Override
    public void log(String message) {
        System.out.println("Logged to file: " + message);
    }
}

// Console Logger
class ConsoleLogger implements Logger {
    @Override
    public void log(String message) {
        System.out.println("Logged to console: " + message);
    }
}

// Logger Factory
interface LoggerFactory {
    Logger createLogger();
}

// File Logger Factory
class FileLoggerFactory implements LoggerFactory {
    @Override
    public Logger createLogger() {
        return new FileLogger();
    }
}

// Console Logger Factory
class ConsoleLoggerFactory implements LoggerFactory {
    @Override
    public Logger createLogger() {
        return new ConsoleLogger();
    }
}

// Client Code
public class LoggerClient {
    public static void main(String[] args) {
        LoggerFactory factory = new ConsoleLoggerFactory();
        Logger logger = factory.createLogger();
        logger.log("This is a log message");
    }
}


```
            
- **Learning and Recall:**
    
    - **Remember the Core Concept:**
        - The Factory Design Pattern provides an interface for creating instances of a class with the flexibility to alter the type of objects created by subclasses.
    - **Examples for Recall:**
        - When dealing with databases, think of how different databases can be connected using different factories.
        - Consider scenarios where logging to different outputs (file, console) is needed, and how factories can provide the necessary loggers.