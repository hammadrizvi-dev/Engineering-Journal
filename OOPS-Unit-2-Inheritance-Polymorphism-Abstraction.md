# OOPS Unit 2 - Inheritance, Polymorphism, Abstraction & Advanced Concepts

---

## 1. Inheritance

Inheritance is a mechanism in which one class acquires properties and behavior of another class.
It represents an **IS-A relationship**.

### Syntax:

```java
class SubClass extends SuperClass {
    // methods and fields
}
```

---

### Types of Inheritance in Java

1. Single Inheritance
2. Multilevel Inheritance
3. Hierarchical Inheritance
4. Multiple Inheritance (Not supported using classes, supported via interfaces)

---

### Important Rules:

* Private members are not inherited
* Default, protected, and public members are inherited

---

## 2. super Keyword

The `super` keyword refers to the immediate parent class object.

### Uses:

1. Access parent class variable
2. Call parent class method
3. Call parent class constructor

---

### Example:

```java
class Animal {
    String color = "White";
}

class Dog extends Animal {
    String color = "Black";

    void printColor() {
        System.out.println(super.color);
    }
}
```

---

## 3. Inheritance Example (Multilevel)

```java
class Animal {
    void eat() {
        System.out.println("Eating");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking");
    }
}

class BabyDog extends Dog {
    void weep() {
        System.out.println("Weeping");
    }
}
```

---

## 4. Object Class

* Root class of Java hierarchy
* Every class implicitly extends Object

### Important Methods:

* `toString()` → returns string representation
* `equals()` → compares objects
* `hashCode()` → returns hash value
* `getClass()` → returns class info
* `finalize()` → cleanup before GC
* `clone()` → creates object copy
* `notify(), notifyAll()` → thread communication

---

## 5. Polymorphism

Polymorphism means **one name, many forms**.

---

### Types:

#### Compile-Time Polymorphism (Static Binding)

* Achieved using method overloading

#### Runtime Polymorphism (Dynamic Binding)

* Achieved using method overriding

---

### Method Overloading Rules:

* Same method name
* Different parameters (number/type/order)
* Cannot overload only by return type

---

### Method Overriding Rules:

* Same method name
* Same parameters
* Must be inheritance relationship
* Access modifier cannot be more restrictive

---

## 6. Dynamic Method Dispatch

* Method call is resolved at runtime
* Based on object type

---

## 7. Abstract Class

An abstract class is declared using `abstract` keyword.
It can have abstract and non-abstract methods.

---

### Rules:

* Cannot create object of abstract class
* Must be inherited
* Child class must implement abstract methods

---

### Example:

```java
abstract class Bike {
    abstract void run();

    void changeGear() {
        System.out.println("Gear changed");
    }
}

class Honda extends Bike {
    void run() {
        System.out.println("Running safely");
    }
}
```

---

## 8. Interface

An interface is a blueprint of a class.

---

### Key Points:

* Methods are public and abstract by default
* Variables are public, static, final
* Supports multiple inheritance

---

### Syntax:

```java
interface Printable {
    void print();
}
```

---

### Example:

```java
class Document implements Printable {
    public void print() {
        System.out.println("Printing document");
    }
}
```

---

## 9. Multiple Inheritance using Interface

Java supports multiple inheritance through interfaces.

```java
interface Father {
    void work();
}

interface Mother {
    void care();
}

class Child implements Father, Mother {
    public void work() {
        System.out.println("Working");
    }

    public void care() {
        System.out.println("Caring");
    }
}
```

---

## 10. Packages

Package is used to group related classes.

---

### Types:

* Built-in packages (java.lang, java.util, java.io)
* User-defined packages

---

### Keywords:

* `package` → define package
* `import` → access classes

---

### Example:

```java
package mypack;

public class A {
    public void msg() {
        System.out.println("Hello");
    }
}
```

---

## 11. final Keyword

Used to restrict modification.

---

### Types:

#### Final Variable

* Value cannot be changed

#### Final Method

* Cannot be overridden

#### Final Class

* Cannot be inherited

---

## 12. Access Modifiers

Access modifiers define visibility.

---

### Types:

#### Private

* Accessible within class only

#### Default

* Accessible within package

#### Protected

* Accessible within package + subclass

#### Public

* Accessible everywhere

---

## Summary

* Inheritance enables reusability
* super keyword connects parent-child
* Object class is root of all classes
* Polymorphism provides flexibility
* Abstract class and interface provide abstraction
* Packages organize code
* final restricts changes
* Access modifiers control visibility

---
