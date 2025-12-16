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
    - Test
- Built-in Data Types: set of values and a set operations on those values.
    - char, strings, int, double (floating point numbers), boolean (true/false)
    - declaration and assignment statements
    - Literal = what you type in the code (ingredients written on paper)
    - Value = what exists in memory when the program runs (actual ingredients in used in the meal)
- Type conversion and casting
    - Id and resolve type errors in order to compile code

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

**Distance Calculation**
```java
public class GreatCircle {
    public static void main(String[] args) {

        // Parse command-line arguments
        double x1 = Double.parseDouble(args[0]);  // latitude 1
        double y1 = Double.parseDouble(args[1]);  // longitude 1
        double x2 = Double.parseDouble(args[2]);  // latitude 2
        double y2 = Double.parseDouble(args[3]);  // longitude 2

        // Convert to radians
        x1 = Math.toRadians(x1);
        y1 = Math.toRadians(y1);
        x2 = Math.toRadians(x2);
        y2 = Math.toRadians(y2);

        // Earth's radius in kilometers
        double r = 6371.0;

        // Great-circle distance formula
        double d = r * 2 * Math.asin(
                Math.sqrt(
                        Math.pow(Math.sin((x2 - x1) / 2), 2)
                                + Math.cos(x1) * Math.cos(x2)
                                * Math.pow(Math.sin((y2 - y1) / 2), 2)
                )
        );

        System.out.println(d + " kilometers");
    }
}
```


### Key Takeaways
- Java is strongly typed - must declare variable types
- `public static void main(String[] args)` is entry point

---

## Module 2: Conditionals and Loops

### Key Concepts
- If-else statements
- Boolean logic (&&, ||, !)
- While loops
    -  Don't forget { } !
- For loops
    - Evaluate an initialization statement
    - Evaluate a boolean expression
    - If true, executed a sequence of statements, then executed an increment statement.
    - Repeat
- Debugging (process of eliminating mistakes)
    - Test many types of inputs
    - Add trace code to find the first error
    - Fix the error
    - Repeat


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

**Loop Patterns**
```java
// Square root calculation
public class Sqrt
{
    public static void main(Stringt[] args)
    {
        double EPS = 1E-15;
        double c = Double.parseDouble(args[0]);
        doubt t = c;
        while (Math.abs(t - c/t) > t*EPS)
            t = (c/t + t) / 2.0
        System.out.println(t);
    }
}
```

```java
// Sum first n integers
int sum = 0;
for (int i = 1; i <= n; i++) { // initialization; boolean expression; increment statement
    sum += i;
}
```
```java
// Subdivisions of a ruler
public class Ruler
{
    public static void main(String[] args)
    {
        int N = Integer.parseInt(args[0]);
        String ruler = " ";
        for (int i = 1; i <= N; i++)
            ruler  = ruler + i + ruler;
        System.out.println(ruler);
    }
}
```
**Loopity-Loops**
```java
// Random Walker

```

### Key Takeaways
- Use for loops when you know iteration count
- Use while loops when condition-based
- Break and continue alter loop flow

---

## Module 3: Arrays

### Key Concepts
- Array Basic Concepts - gives ability to store and process large amounts of data
    - Indexed sequence of values of the same type
    - Given i, the operation of accessing the value of a[i] is efficient
    - Declare an array -> double[] a;
    - Create an array of a given length -> a = new double[1000];
    - Refer to an array entry by index -> a[i] = b[j] + c[k];
    - Refer to the length of an array -> a.length;
    - Declare, create, and initialize in one statement -> double[] a = new double[1000];
    - Initialize to literal values -> double[] x = {0.3, 0.6, 0.1};
    - Copy an array: create a new array, then copy all values
    ```java
       double[] b = new double[a.length];
       for (int i = 0; i <  a.length; i++)
           b[i] = a[i];
     ```
    - Use nested for loops to put all the cards in the deck
     ```java
	String[] rank = {"2", "3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K", "A"};
	String[] suit = {"C", "D", "H", "S"};
	String[] deck = new String[52];
     
       for (int j = 0;  j < 4; j++)
         for (int i = 0;  i < 13; i++)
	     deck[i + 13*j] = rank[i] + suit[j];
     ```
    - Shuffle the deck, then deal (Fisher-Yates shuffle algorithm)
    ```java
	//Shuffle the deck
	for (int i = 0; i < 52; i++)
	{
	    int r = i + (int) (Math.random() * (52-i)); //Calcs random index r. (int) truncates
	    String t = deck[r]; //t temporarily holds the card at position r
	    deck[r] = deck[i]; //r gets card from position i
	    deck[i] = t; //position i gets the card that was at position r (stored in t)
	}
	//Prints the first N cards from the shuffled deck
	for (int i = 0; i < N; i++)
	    System.out.print(deck[i]);
	System.out.println();
     ```
    - Coupon collector simulation - simulates how many random draws it takes to collect M distinct items
    ```java
	public class Coupon
	{
	    public static void main(String[] args)
	    {
		int M =Integer.parseInt(args[0]); //reads and converts command line argument to an integer
		int cards = 0; // number of cards collected. tracks total number draws
		int distinct = 0; // number of distinct cards. tracks unique cards collected
		
		boolean[] found = new boolean[M];//found[i] is true if you;ve collected card i at least onece
		while (distinct < M) // loop continues until distinct == M
		{
		    int r = (int) (Math.random() * M);//generates random index 0 to (M-1)
		    cards++;//increments total
		    if (!found[r])//if we haven't seen card r before, increment the distinct counter
		    {
			distinct++;
			found[r] = true //mark card as found
		    }
		}
		System.out.println(cards);//prints the total number of draws need to complete the collection
	}
	//On average, collecting M distinct coupon requires M * ln(M) random draws = ~205
     ```

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


[← Back to Computer Science Fundamentals](./README.md)
