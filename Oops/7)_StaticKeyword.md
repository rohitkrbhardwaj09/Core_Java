### `static` Keyword in Java

---

#### 🔹 What is `static` in Java?

* `static` is a keyword used for memory management.
* It can be applied to **variables, methods, blocks, and nested classes**.
* Belongs to the **class rather than instances** (objects).

---

#### 🔹 Static Variables (Class Variables)

* Shared among all instances of a class.
* Memory is allocated only once when the class is loaded.

**Example:**

```java
class Employee {
    static String company = "ABC Corp";  // shared by all
    String name;

    Employee(String name) {
        this.name = name;
    }
}
```

---

#### 🔹 Static Methods

* Can be called **without creating an object**.
* Can access **static data members** only.
* **Cannot access instance (non-static) variables or methods directly.**

**Example:**

```java
class MathUtils {
    static int square(int x) {
        return x * x;
    }
}
```

**Usage:**

```java
int result = MathUtils.square(5);  // No need to create an object
```

---

#### 🔹 Static Blocks

* Used to **initialize static variables**.
* Executes when the class is loaded (before main method or constructor).

**Example:**

```java
class Config {
    static int threshold;

    static {
        threshold = 100;  // static block initialization
        System.out.println("Static block executed");
    }
}
```

---

#### 🔹 Static Classes (Nested Static Classes)

* A static **nested class** does not need a reference to an outer class.
* Can access only **static members of the outer class**.

**Example:**

```java
class Outer {
    static int outerStatic = 10;

    static class Inner {
        void display() {
            System.out.println("Outer static: " + outerStatic);
        }
    }
}
```

---

#### 🔹 Key Points Summary

* `static` members belong to the **class**, not objects.
* **Efficient memory usage** – especially for constants and utility methods.
* Static methods cannot use `this` keyword.
* Common use cases:

  * Constants (`static final`)
  * Utility/helper methods
  * Counters/shared resources
  * Singleton classes
