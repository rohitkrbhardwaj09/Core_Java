# `this` Keyword in Java

The `this` keyword in Java is a reference variable that refers to the current object. It is commonly used to:

- Differentiate between instance variables and parameters with the same name
- Invoke current class methods or constructors
- Pass the current object as a parameter
- Return the current class instance

## Uses of `this` Keyword

- **Referring to the current class instance variable**  
  When local variables (such as parameters of a method or constructor) have the same name as instance variables, `this` can be used to refer to the instance variables.

  ```java
  class Example {
      int x;

      Example(int x) {
          this.x = x; // Refers to the instance variable
      }
  }
  ```
  

## Example

```java
class Student {
    int id;
    String name;

    // Constructor using 'this' to refer to instance variables
    Student(int id, String name) {
        this.id = id;
        this.name = name;
    }

    // Method using 'this' to call another method
    void display() {
        this.printDetails();
    }

    void printDetails() {
        System.out.println("ID: " + id + ", Name: " + name);
    }

    // Method returning 'this' for method chaining
    Student updateName(String newName) {
        this.name = newName;
        return this;
    }

    // Method accepting current object as a parameter
    void compare(Student other) {
        if (this.id == other.id) {
            System.out.println("Same ID");
        } else {
            System.out.println("Different IDs");
        }
    }

    public static void main(String[] args) {
        Student s1 = new Student(101, "Alice");
        s1.display();                       // Calls printDetails using this
        s1.updateName("Alicia").display();  // Method chaining with return this

        Student s2 = new Student(102, "Bob");
        s1.compare(s2);                     // Passes current object as parameter
    }
}
```
