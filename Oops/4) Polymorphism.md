# 🔹 Polymorphism in Java 
### 📘 Meaning:
> `POLY` = MANY <br/>
> `MORPH` = FORMS <br/>
> Polymorphism means: Ek kaam ko alag-alag tarike se karna. 

#### Polymorphism allows us to perform one action in different ways.

---

# 🔸 Types of Polymorphism in Java:
| Type                          | Also Called        | When it Happens    |
| ----------------------------- | ------------------ | ------------------ |
| **Compile-Time Polymorphism** | Method Overloading | During Compilation |
| **Runtime Polymorphism**      | Method Overriding  | During Execution   |

---
## ✅ 1. Compile-Time Polymorphism (Method Overloading)
---

### 📘 Definition:
> Method Overloading means defining multiple methoda with the same name in the same class, but with different parameters (number, type, or order).

## Rules
- Method name must be same
- Parameter should be different
- Can differ by -
  - Number of parameters
  - Type of parameters
  - Order of parameters
- Happens at Compile Time → also called Compile-Time Polymorphism
- Return type can be same or different, but it does NOT decide overloading

### Example:
```java
  class Calculator {
    // method 1
    void add(int a, int b){
      System.out.println("Sum (int): "+ (a+b));
    }

    // method 2 - different number of parameters
    void add(int a, int b, int c){
      System.out.println("Sum (3 int): "+ (a+b+c));
    }

    // method 3 - different parameter type
    void add(double a, double b){
      System.out.println("Sum (double): "+ (a+b));
    }
  
    public static void main(String[] args){
      Calculator calc = new Calculator();
      calc.add(2,3);      // calls method 1
      calc.add(2,3,4);    // calls method 2
      calc.add(2.5,3.5);  // calls method 3
    }
  }
```

---

## ❗ Notes to Remember:
- ✅ Overloading improves readability of code.
- ❌ Method overloading cannot be done only by changing return type.
- ✅ It’s limited to same class (not between parent-child like overriding).

---

## 📦 Real-Life Analogy:
- ATM Machine
- Insert debit card → withdraw
- Insert credit card → check balance
- Insert UPI QR → scan & pay

> 👉 Same machine (method name), but different inputs, different behavior

---

## 🔍 Why Do We Use the Same Method Name?
- Because the **action is conceptually the same**, only **inputs differ**.
- Improves code **readability**, **reusability**, and makes the code **intuitive**.

---

# 🛠️ Constructor Overloading

## ❓ What is Constructor Overloading?
**Constructor Overloading** means creating **multiple constructors** in the same class with **different parameter lists**.

---

## ✅ Key Points

- 🔁 **Same class**, multiple constructors
- ✏️ Constructors have **same name** as class
- 📥 Different in terms of **number, type, or order** of parameters
- 🚀 Helps in **object initialization** in **different ways**
- ⏱️ Occurs at **Compile Time**

---

## 💡 Why Use Constructor Overloading?

- Flexibility to initialize objects with **different levels of data**
- Avoids code duplication
- Improves code readability

---

## 💻 Java Program Example

```java
class Student {
    String name;
    int age;

    // Default constructor
    Student() {
        name = "Unknown";
        age = 0;
    }

    // Constructor with 1 parameter
    Student(String n) {
        name = n;
        age = 0;
    }

    // Constructor with 2 parameters
    Student(String n, int a) {
        name = n;
        age = a;
    }

    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }

    public static void main(String[] args) {
        Student s1 = new Student();
        Student s2 = new Student("Ravi");
        Student s3 = new Student("Priya", 21);

        s1.display();
        s2.display();
        s3.display();
    }
}
```

---

from pathlib import Path

# Create notes for passing parameters to main() in markdown format
main_params_md = """
# 🧵 Passing Parameters to `public static void main(String[] args)` in Java

## 🔹 What is `String[] args`?
- It is the parameter of the **main() method**.
- It allows the program to **accept command-line arguments** (inputs) when the Java program is run.

---

## 📘 Full Method Signature
```java
public static void main(String[] args)
```
- public: accessible from anywhere
- static: no need to create object to call main()
- void: does not return anything
- String[] args: array of String objects (stores inputs from the command line)

## 📥 How to Pass Parameters?
You pass arguments from the command line when running your .class file.

💻 **Example Code:**
```java
public class CommandLineExample {
    public static void main(String[] args) {
        
        for(String s:args) {
            System.out.println("Argument :" + s);
        }

        System.out.println(args.length);
    }
}
```
Step 1: <br/> ![image](https://github.com/user-attachments/assets/84e8ae71-b258-4175-b8b9-e1873d5008bf) <br/>
Step 2: Search for your file, and click OK <br/>
        ![image](https://github.com/user-attachments/assets/8ec398af-1073-42b2-967b-31224896f27d) <br/>
Step 3: Provide String in field 2 as I have provided "Welcome to Java, My name is Rohit" <br/>
        ![image](https://github.com/user-attachments/assets/a9b3c7a8-a862-40d8-9b4c-ab6d10d28c56) <br/>
Output: <br/> ![image](https://github.com/user-attachments/assets/f58acb15-55a2-4bae-9339-69c64dc869e8) <br/>

----

# 🔁 Multiple `main()` Methods in a Single Java Class

## ❓ Question: Can We Create Multiple `main()` Methods in One Class?
### ✅ Yes, we can **overload** the `main()` method in a single class.

---

## 🔹 How is it Possible?
- Java allows **method overloading**, and `main()` is just another method.
- You can define multiple `main()` methods with **different parameter lists**.
- But the **JVM always starts with** this signature:
```java
public static void main(String[] args)
```

## ✅ Use Case
> Overloaded `main()` methods can be used for **testing, method chaining**, or calling from inside the standard main().

## Java Example
```java
public class MultiMainExample {

    // JVM Entry Point
    public static void main(String[] args) {
        System.out.println("Main with String[] args");
        main(10);
        main("Hello", 20);
    }

    // Overloaded main method - int parameter
    public static void main(int x) {
        System.out.println("Main with int: " + x);
    }

    // Overloaded main method - String and int parameter
    public static void main(String s, int x) {
        System.out.println("Main with String and int: " + s + ", " + x);
    }
}
```

### Output
```java
Main with String[] args
Main with int: 10
Main with String and int: Hello, 20
```

## 🧠 Important Notes
| Concept               | Explanation                                     |
| --------------------- | ----------------------------------------------- |
| JVM Entry Point       | Always `public static void main(String[] args)` |
| Overloading Allowed   | Yes, with different parameters                  |
| Called Automatically? | ❌ Only standard main is called by JVM           |
| Manual Call Required? | ✅ You must call overloaded versions from code   |

## 🚫 Misunderstanding Alert
> Defining overloaded main() methods does not mean JVM will call them.
> Only the standard main(String[] args) is auto-invoked.

## 🧠 Summary
- You can create multiple main() methods via overloading.
- JVM only calls the version with String[] args automatically.
- Overloaded versions must be called manually.
- Useful for testing, demo, and custom logic.

---

---

