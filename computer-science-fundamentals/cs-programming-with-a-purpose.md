# CS: Programming with a Purpose

**Course**: [Computer Science: Programming with a Purpose](https://www.coursera.org/learn/cs-programming-java)  
**Platform**: Coursera (Princeton University)  
**Started**: November 2024  
**Language**: Java  

## Course Overview

Foundational computer science course covering programming basics, algorithms, and computational thinking using Java.

---

## Module 1: Basic Programming Concepts

### Key Concepts
- Programming: make a computer do what you want.
- Program Development:
    - Edit
    - Compile: translates human readable code into machine code.
    - Run
- Built-in Data Types: set of values and a set operations on those values.
    - char, strings, int, double (floating point numbers), boolean (true/false)
    - declaration and assignment statements
    - Literal = what you type in the code (ingredients written on paper)
    - Value = what exists in memory when the program runs (actual ingredients in used in the meal)
- Type conversion and casting
- Input/output using StdIn/StdOut

### Code Examples

**Hello World**
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

**Reading Input**
```java
public class Addition {
    public static void main(String[] args) {
        int a = StdIn.readInt();
        int b = StdIn.readInt();
        int sum = a + b;
        StdOut.println("Sum = " + sum);
    }
}
```

### Key Takeaways
- Java is strongly typed - must declare variable types
- `public static void main(String[] args)` is entry point
- Use StdIn/StdOut library for simplified I/O

### Assignment Notes
- **Problem**: Calculate distance between two points
- **Approach**: Use Math.sqrt() and Math.pow()
- **Gotcha**: Remember to use doubles for division

---

## Module 2: Conditionals and Loops

### Key Concepts
- If-else statements
- Boolean logic (&&, ||, !)
- While loops
- For loops

### Code Examples

**Conditional Logic**
```java
if (x > 0) {
    StdOut.println("Positive");
} else if (x < 0) {
    StdOut.println("Negative");
} else {
    StdOut.println("Zero");
}
```

**Loop Pattern**
```java
// Sum first n integers
int sum = 0;
for (int i = 1; i <= n; i++) {
    sum += i;
}
```

### Key Takeaways
- Use for loops when you know iteration count
- Use while loops when condition-based
- Break and continue alter loop flow

### Assignment Notes
- **Problem**: Implement a game simulation
- **Learned**: Nested loops for 2D problems
- **Time spent**: 2 hours

---

## Module 3: Arrays

### Key Concepts
- Array declaration and initialization
- Accessing elements by index
- Array length property
- Common array operations (search, reverse, etc.)

### Code Examples

**Array Basics**
```java
// Declaration
int[] numbers = new int[10];

// Initialization
int[] primes = {2, 3, 5, 7, 11};

// Iteration
for (int i = 0; i < primes.length; i++) {
    StdOut.println(primes[i]);
}
```

### Key Takeaways
- Arrays are fixed size in Java
- Zero-indexed (first element is arr[0])
- .length gives size (not a method, it's a property)

---

## Week 4: Functions (Methods)

*[To be completed]*

---

## Week 5: Recursion

*[To be completed]*

---

## Common Patterns & Tricks

### Reading Command Line Arguments
```java
public static void main(String[] args) {
    int n = Integer.parseInt(args[0]);
    String name = args[1];
}
```

### StdDraw for Graphics
```java
StdDraw.setScale(0, 100);
StdDraw.point(50, 50);
StdDraw.show();
```

---

## Personal Insights

- **Connection to R**: Java's strongly typed system is stricter than R
- **Debugging approach**: Use print statements liberally to trace values
- **Best practice**: Write small functions and test incrementally

---

## Resources

- [Course Website](https://introcs.cs.princeton.edu/java/home/)
- [Java API Documentation](https://docs.oracle.com/javase/8/docs/api/)
- [Princeton's Standard Libraries](https://introcs.cs.princeton.edu/java/stdlib/)

---

[← Back to Computer Science Fundamentals](./README.md)
