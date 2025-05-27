### Inheritance in Java

---

### 🔹 What is Inheritance?

* Inheritance is a mechanism in Java by which **one class acquires the properties and behaviors (fields and methods)** of another class.
* Helps in **code reusability** and **method overriding**.

---

### 🔹 Basics of Inheritance

* The class that inherits is called the **subclass** (or child class).
* The class being inherited from is called the **superclass** (or parent class).
* Use the `extends` keyword.

**Syntax:**

```java
class Superclass {
    // fields and methods
}

class Subclass extends Superclass {
    // additional fields and methods
}
```

---

### 🔹 Extending Classes

* Java uses the `extends` keyword to implement inheritance.
* The subclass inherits **non-private members** (fields and methods) from the superclass.

**Example:**

```java
class Animal {
    void eat() {
        System.out.println("This animal eats food");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}
```

**Usage:**

```java
Dog d = new Dog();
d.eat();   // inherited method
```

---

### 🔹 Superclass and Subclass

* **Superclass**: The parent class whose members are inherited.
* **Subclass**: The child class which inherits members from the superclass.

**Example:**

```java
class Vehicle {
    void start() {
        System.out.println("Vehicle started");
    }
}

class Car extends Vehicle {
    void drive() {
        System.out.println("Car is driving");
    }
}
```

---

### 🔹 Types of Inheritance in Java

Java supports the following types of inheritance:

#### 1. Single Inheritance

* A class inherits from one superclass.

**Example:**

```java
class A {
    void show() {
        System.out.println("Class A");
    }
}

class B extends A {
    void display() {
        System.out.println("Class B");
    }
}
```

#### 2. Multiple Inheritance (via Interfaces)

* Java **does not support multiple inheritance with classes** to avoid ambiguity.
* Achieved using **interfaces**.

**Example:**

```java
interface A {
    void methodA();
}

interface B {
    void methodB();
}

class C implements A, B {
    public void methodA() {
        System.out.println("Method A");
    }
    public void methodB() {
        System.out.println("Method B");
    }
}
```

#### 3. Multilevel Inheritance

* A class inherits from a class which itself inherits from another class.

**Example:**

```java
class A {
    void methodA() {
        System.out.println("A's method");
    }
}

class B extends A {
    void methodB() {
        System.out.println("B's method");
    }
}

class C extends B {
    void methodC() {
        System.out.println("C's method");
    }
}
```

#### 4. Hierarchical Inheritance

* Multiple classes inherit from a single superclass.

**Example:**

```java
class Parent {
    void parentMethod() {
        System.out.println("Parent method");
    }
}

class Child1 extends Parent {
    void child1Method() {
        System.out.println("Child1 method");
    }
}

class Child2 extends Parent {
    void child2Method() {
        System.out.println("Child2 method");
    }
}
```

---

### 🔹 Summary

* Inheritance promotes code reuse and method overriding.
* Java supports: single, multilevel, hierarchical inheritance, and multiple inheritance via interfaces.
* Use `extends` for class inheritance and `implements` for interface inheritance.
