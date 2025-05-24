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

    
