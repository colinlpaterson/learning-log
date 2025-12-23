# CS: Programming with a Purpose

**Course**: [Computer Science: Programming with a Purpose](https://www.coursera.org/learn/cs-programming-java)  
**Platform**: Coursera (Princeton University)  
**Started**: November 2025
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
- Two-Dimensional Arrays: doubly-indexed sequence of values of the same type
    - Main purpose: facilitates storage and manipulation of data
    - With an index, a program can instantly access a given value
    - double[][] a = new double[100][100];
    ```java
	// 2D array: self-avoiding random walks. Can model behavior in physics
	public class SelfAvoidingWalker
	{
    	     public static void main(String[] args)
    	{
                  // Read grid size from first command line argument
                  int N = Integer.parseInt(args[0]); 
        
                  // Read number of simulation trials from second argument
                  int trials = Integer.parseInt(args[1]); 
        
                  // Counter for walks that get trapped (surrounded by visited cells)
                  int deadEnds = 0;
        
                  // Run multiple trials to get statistical results
                  for (int t = 0; t < trials; t++)
                  {
                      // Create NxN grid to track visited positions
                      boolean[][] a = new boolean[N][N]; // false = unvisited, true = visited
            
                      // Start walker in the center of the grid
                      int x = N/2, y = N/2;
            
                      // Continue walking while not at the edge of the grid
                      // (leaving 1-cell border to avoid array bounds issues)
                      while (x > 0 && x < N-1 && y > 0 && y < N-1)
            {
                          // Check if walker is surrounded on all 4 sides (DEAD END)
                          // If all adjacent cells have been visited, walker is trapped
                          if (a[x-1][y] && a[x+1][y] && a[x][y-1] && a[x][y+1])
                          { 
                              deadEnds++;  // Count this as a dead end
                              break;       // Exit this trial
                          }
                
                          // Mark current position as visited
                          a[x][y] = true;
                
                          // Generate random number to choose direction
                          double r = Math.random(); // Returns value between 0.0 and 0.999...
                
                          // Move in a random direction, but ONLY if that cell hasn't been visited
                          // This is what makes it "self-avoiding"
                          if (r < 0.25)              // 25% chance: try to move RIGHT
                          { 
                               if (!a[x+1][y]) x++;  
                          }
                          else if (r < 0.50)         // 25% chance: try to move LEFT
                          { 
                               if (!a[x-1][y]) x--;  
                          }
                          else if (r < 0.75)         // 25% chance: try to move DOWN
                          { 
                              if (!a[x][y+1]) y++;   
                          }
                          else if (r < 1.00)         // 25% chance: try to move UP
                          {                          
                              if (!a[x][y-1]) y--;   
                          }
                          // NOTE: If chosen direction is already visited, walker stays put
                      }
                 }
        
              // Calculate and print percentage of walks that ended in dead ends
              System.out.println(100*deadEnds/trials + "% dead ends");
              }
     }
	
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

## Module 4 Input and Output

### Key Concepts
- Input and Output
    - Abstraction is something that exists only as an idea
    - Good abstractions simplify our view of the world by unifying real-world artifacts
    - No limits on the size of input / output stream
    - Standard input is an abstraction for providing input to a program while it is running
    - Piping |: connect standard output of one program to standard input of another
    - Streaming algorithms enable our programs to handle much more data than computers can store
- Standard Drawing
    - stdDraw library (line, point, text, circle, square, polygon, picture)
    - Example
```java
   public class Triangle
{
    public static void main(String[] args)
    {
        // Calculate sqrt(3)/2 ≈ 0.866
        double c = Math.sqrt(3.0) / 2.0;
        
        // Set pen thickness for drawing
        StdDraw.setPenRadius(0.01);
        
        // Draw horizontal line from (0,0) to (1,0). This forms the BASE of an equilateral triangle
        StdDraw.line(0.0, 0.0, 1.0, 0.0);
        
        // Draw a point at (0.5, c/3.0)
        // c/3 = sqrt(3)/6 ≈ 0.289
        // This marks the CENTROID of the equilateral triangle
        // (the balance point, located 1/3 up from the base)
        StdDraw.point(0.5, c/3.0);
        
        // Draw text "Hello World" centered at (0.5, 0.5)
        StdDraw.text(0.5, 0.5, "Hello World");
     }
}
```
- Fractal Drawings
```java
//Sierpinski triangle fractal through random iteration.
public class Chaos
{
    public static void main(String[] args)
    {
        // Read number of iterations from command line
        int trials = Integer.parseInt(args[0]);
        
        // Calculate sqrt(3)/2 ≈ 0.866 (height of equilateral triangle with base=1)
        double c = Math.sqrt(3.0) / 2.0;
        
        // Define x-coordinates of the three vertices of an equilateral triangle
        // Vertex 1: (0.0, 0.0) - bottom left
        // Vertex 2: (1.0, 0.0) - bottom right  
        // Vertex 3: (0.5, c)   - top center
        double[] cx = { 0.000, 1.000, 0.500 };
        
        // Define y-coordinates of the three vertices
        double[] cy = { 0.000, 0.000, c };
        
        // Set the pen thickness for drawing points
        StdDraw.setPenRadius(0.01);
        
        // Start at the origin (0, 0)
        double x = 0.0, y = 0.0;
        
        // Main iteration loop - the "chaos game" algorithm
        for (int t = 0; t < trials; t++)
        {
            // Randomly select one of the three vertices (0, 1, or 2)
            int r = (int) (Math.random() * 3);
            
            // Move halfway from current position toward the randomly chosen x vertex
            x = (x + cx[r]) / 2.0;
            
            // Update y-coordinate the same way
            y = (y + cy[r]) / 2.0;
            
            // Plot the new point
            StdDraw.point(x, y);
        }
    }
}
```
- Animation
```java
public class BouncingBall
{
    public static void main(String[] args)
    {
        // Initial position of ball center (x=0.480, y=0.860)
        // Starting near upper-right area of the canvas
        double rx = .480, ry = .860;
        
        // Velocity components (speed and direction)
        // vx = horizontal velocity (moving right)
        // vy = vertical velocity (moving up)
        double vx = .015, vy = .023;
        
        // Radius of the ball (5% of canvas width)
        double radius = .05;
        
        // Set coordinate system from -1.0 to +1.0 in x-direction
        StdDraw.setXscale(-1.0, +1.0);
        
        // Set coordinate system from -1.0 to +1.0 in y-direction
        // Creates a 2x2 square canvas centered at origin
        StdDraw.setYscale(-1.0, +1.0);
        
        // Infinite animation loop - runs forever
        while(true)
        {
            // Clear the canvas by drawing a light gray background square
            // Covers entire canvas from -1 to +1 in both directions
            StdDraw.setPenColor(StdDraw.LIGHT_GRAY);
            StdDraw.fillSquare(0.0, 0.0, 1.0);
            
            // Check for collision with LEFT or RIGHT wall
            // If ball's next position would hit wall, reverse horizontal velocity
            if (Math.abs(rx + vx) + radius > 1.0) vx = -vx;
            
            // Check for collision with TOP or BOTTOM wall
            // If ball's next position would hit wall, reverse vertical velocity
            if (Math.abs(ry + vy) + radius > 1.0) vy = -vy;
            
            // Update ball's x-position based on velocity
            rx = rx + vx;
            
            // Update ball's y-position based on velocity
            ry = ry + vy;
            
            // Set drawing color to black for the ball
            StdDraw.setPenColor(StdDraw.BLACK);
            
            // Draw the ball as a filled circle at position (rx, ry)
           
            StdDraw.filledCircle(rx, ry, radius); 
            
            // Display the frame and pause for 20 milliseconds
            // Creates smooth animation at ~50 frames per second
            StdDraw.show(20);
        }
    }
}
```
 



[← Back to Computer Science Fundamentals](./README.md)
