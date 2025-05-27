### Understanding `System.out.println` in Java

---

#### 🔹 What is `System.out.println`?

* Used to **print text to the console** followed by a newline.
* It is part of Java's **standard library**.

---

#### 🔹 Breakdown of `System.out.println`

```java
System.out.println("Hello, World!");
```

| Component   | Meaning                                                                 |
| ----------- | ----------------------------------------------------------------------- |
| `System`    | A final class from `java.lang` package. Contains useful static members. |
| `out`       | A static `PrintStream` object in the `System` class. Standard output.   |
| `println()` | A method of `PrintStream` that prints a message followed by a newline.  |

---

#### 🔹 How It Works

* `System.out` gives access to the console output stream.
* `println()` prints the argument and moves the cursor to the next line.
* `print()` does the same **without** moving to the next line.

---

#### 🔹 Examples

```java
System.out.println("Line 1");
System.out.println("Line 2");
```

**Output:**

```
Line 1
Line 2
```

```java
System.out.print("Hello ");
System.out.print("World");
```

**Output:**

```
Hello World
```

---

#### 🔹 Behind the Scenes

* `System.out` is a predefined object of `PrintStream` connected to the console.
* `println()` internally calls native code to handle the output.

---

#### 🔹 Summary

* `System.out.println` is the most common way to **display output in Java**.
* Ideal for debugging, console apps, and simple text-based interaction.
