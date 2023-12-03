
# Liskov Substitution Principle

<aside> 🤔 **Objects of a superclass should be replaceable with objects of a subclass.**

</aside>

# 🥺 Problem

- We are making a Software that can give any car Self Driving Capability.
- We have two types of cars, `PetrolCar` and `DieselCar`.

```java
@Data
public abstract class Car {
    int licensePlate;
    String color;
    public abstract void accelerate();
    public abstract void shiftUp();
}

@Data
class PetrolCar extends Car {
    @Override
    public void accelerate() {
        // implementation logic
    }
    @Override
    public void shiftUp() {
        // implementation logic
    }
}

@Data
class DieselCar extends Car {
    @Override
    public void accelerate() {
        // implementation logic
    }

    @Override
    public void shiftUp() {
        // implementation logic
    }
}
```

- Okay. Looks good. Now, we want to add another Car type, `ElectricCar` , but Electric Cars cannot Shift! So what should we do?

```java
@Data
public class ElectricCar extends Car {
    @Override
    public void accelerate() {
        // implementation logic
    }
    @Override
    public void shiftUp() {
        throw new UnsupportedOperationException();
    }
}
```

<aside> 😨 **You have violated the Liskov Substitution Principle!**

</aside>

### Why?

- Just to make the compiler shut up, we just threw an Exception, but this is not ideal. I mean we can do better. Liskov Substitution Principle checks whether all implemented methods are doing what they are **supposed to do**.

# ✅ Solution

- Move the `shiftUp` method to a different `Interface`.

```java
@Data
public abstract class Car {
    int licensePlate;
    String color;
    public abstract void accelerate();
}
public interface GearShifter {
    void shiftUp();
    void shiftDown();
}
@Data
class PetrolCar extends Car implements GearShifter {
    @Override
    public void accelerate() {
        // implementation logic
    }
    @Override
    public void shiftUp() {
        // implementation logic
    }

    @Override
    public void shiftDown() {
        // implementation logic
    }
}

@Data
class DieselCar extends Car implements GearShifter {
    @Override
    public void accelerate() {
        // implementation logic
    }

    @Override
    public void shiftUp() {
        // implementation logic
    }
    @Override
    public void shiftDown() {
        // implementation logic
    }
}
@Data
public class ElectricCar extends Car {
    @Override
    public void accelerate() {
        // implementation logic
    }
}
```

<aside> 😃 **Now you are adhering to the Liskov Substitution Principle.**

</aside>

- You can freely substitute subclasses of a parent and expect the same behavior out of them.