# Encapsulation

**Encapsulation** in Java is one of the four fundamental Object-Oriented Programming (OOP) concepts (along with Inheritance, Polymorphism, and Abstraction). It refers to the practice of **wrapping data (variables) and code (methods) together as a single unit** and restricting direct access to some of the object's components.

- Every variable should be private.
- For every variable there should be two method to assign value to it and another to access the assigned value from it (getter & setter)
- variable can be operated only through methods.

## Key Features of Encapsulation:
1) **Data Hiding:** The internal representation of an object is hidden from the outside. Access is only allowed through public methods (getters and setters).

2) **Improved Security:** Sensitive data is protected from unauthorized access.

3) **Control:** You can control how important variables in your code are accessed and modified.

## How to Achieve Encapsulation in Java:
- Declare class variables as `private`.
- Provide public getter and setter methods to access and update the value of private variables.

**Example:**
```java
public class Employee {
    // private data members
    private String name;
    private int age;

    // public getter and setter methods
    public String getName() {
        return name;
    }

    public void setName(String newName) {
        name = newName;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int newAge) {
        if (newAge > 0) {
            age = newAge;
        }
    }
}
```

**Usage:**
```java
public class Main {
    public static void main(String[] args) {
        Employee emp = new Employee();
        emp.setName("John");
        emp.setAge(30);

        System.out.println(emp.getName()); // Output: John
        System.out.println(emp.getAge());  // Output: 30
    }
}
```

## Benefits of Encapsulation:
- Maintains the integrity of the data.
- Makes the code easier to manage and understand.
- Increases flexibility and reusability.
- Helps in achieving modularity in code.

---

# Real-world Analogy

## 🏦 Example: ATM Machine (Encapsulation in real life)
Imagine using an ATM (Automated Teller Machine).
- You insert your card and enter a PIN to access your account.
- You withdraw or deposit money using buttons (the interface).
- But you cannot see or directly change the bank’s internal data (like your account balance or transaction logs).

## 🔐 How this relates to encapsulation:
Real-World Element	| Java Equivalent
------------------ | ----------------
ATM machine	| Java class
Card and PIN	| Access control (private data + methods)
Withdraw/deposit buttons	| Public methods (getters/setters)
Bank database |	Private fields (account data)

So, in Java:

- You keep your data (balance, accountNumber) private.
- You expose only safe operations (withdraw(), deposit()) via public methods.
- This way, unauthorized or unsafe access is prevented.

## 💡 Why this is useful:
- It prevents people (or code) from:
- Changing the account balance directly (e.g., balance = -9999)
- Accessing sensitive data without proper checks
