# Linear Algebra: Linear Systems and Matrix Equations

**Course**: [Linear Algebra: Linear Systems and Matrix Equations](https://www.coursera.org/learn/linear-systems-and-matrix-equations)  
**Platform**: Coursera (John Hopkins University)  
**Started**: January 2026


## Course Overview

Covers matrices, vector and matrix equations, linear transformations

---

## Module 1: Introduction to Matrices

### Key Concepts

- A function is linear if all terms are degree 0 or 1
  - 2x + 3y = 4
- A solution of a system of linear equations is the set of points that make every equation in the system true.
- Solutions of linear systems correspond to how lines can meet
  - 3 ways lines can meet:
    - 1 solution, 0 solution, inf solutions
- A linear system is consistent if either 1 or inf solutions exist
- Equivalent linear systems have the same solution set
- 3 elementary row operations (ERO)
  - Replacement: replace one row by the sum of itself and multiple of another row
  - Interchange: swap position of 2 rows
  - Scaling: multiply all entries in a row by a non-zero constant
- Two matrices are row-equivalent if there is a sequence of EROs that transforms one into another
  - All EROs are reversable
  - EROs do not change solution set of the linear system
- **Important Questions**
  - Q1: Is the system consistent?
  - Q2: If consistent, is the solution unique(1 or inf.)
  
**Row Reduction Echelon Form**

- A matrix is in row echelon (steps) form if:
    -All non zero rows are above any rows of all zeros
    - Each leading entry of a row is in a column to the right of the leading entry of the row above it
    - All entries in a column below a leading entry are zero
- A matrix is in row reduced echelon form (rref) if:
    - The first three conditions are met
    -Leading entry in each row is 1
    - Each leading 1 is the only non zero entry in its column
- A pivot position in a matrix is the location corresponding to the leading 1 in rref.
- A pivot column is a column of matrix A that contains a pivot position.
- A column has a free variable when it does NOT contain a pivot (leading 1) after ref or rref. Free variables have infinitely many solutions.
      x₁  x₂  x₃  x₄
    [1   2   0   3 | 5]
    [0   0   1   4 | 6]
    [0   0   0   0 | 0]
     ↑   ↑   ↑   ↑
 pivot free pivot free

**Key idea**: can't see pivots of matrix A unless you convert to ref(A) or rref(A)
- Zero matrix is rref (trivially); 0 pivots
- **Theorem**: A system of linear equations is consistent if and only if the rightmost column of its augmented matrix is not a pivot column (the constants).

```{r}
library(pracma)

# Finding Solutions to Augmented Matrices ----


A2 <- matrix(c(1, 3, 4, 7,
              3, 9, 7, 6
              ), 
            nrow = 2, byrow = TRUE)

A2

A2_rref <- rref(A2)

A2_rref

```

---

## Module 2: Vector and Matrix Equations

### Key Concepts

#### Vectors
- **Vector**: A matrix with only one column
- **Vector Addition**: Visually: Creates the diagonal of the parallelogram formed by the two vectors
  - Addition is **commutative**: u + v = v + u (order doesn't matter)
  - Addition is **associative**: (u + v) + w = u + (v + w) (parentheses don't matter)
  - Addition has an **identity element**: v + 0 = v (the zero vector)
- **Scalar Multiplication**: Stretches or shrinks the vector (and reverses direction if the scalar is negative)
- **The zero vector** 0 is the vector whose entries are all 0

#### Linear Combinations and Span

- A **linear combination** of vectors v₁, v₂, ..., vₚ in ℝⁿ with weights (scalars) c₁, c₂, ..., cₚ in ℝ is the vector :y = c₁v₁ + c₂v₂ + ⋯ + cₚvₚ
- The **span** of vectors v₁, v₂, ..., vₚ is the set of all linear combinations of these vectors. This set is denoted Span{v₁, v₂, ..., vₚ}.

#### Geometric Interpretation of Span

- **Span of a single vector**:
  - If v is a nonzero vector in ℝ³, then Span{v} is the set of all scalar multiples of v
  - Geometrically: Span{v} is the **line** in ℝ³ through v and the origin

- **Span of two vectors**:
  - If u and v are nonzero vectors in ℝ³, then there are two possibilities:
    - **Case 1**: If u is a scalar multiple of v (vectors are parallel), then Span{u, v} is a **line** through the origin
    - **Case 2**: If u is not a scalar multiple of v (vectors are not parallel), then Span{u, v} is the **plane** in ℝ³ that contains u, v, and the origin 0

### Matrix Equations

#### Theorem: Matrix Equations, Vector Equations, and Linear Systems

Let A be an m×n matrix with columns a₁, a₂, ..., aₙ. Let b be a vector in ℝᵐ. Then the **matrix equation**

Ax = b

has the same solution set as the **vector equation**

x₁a₁ + x₂a₂ + ⋯ + xₙaₙ = b

and the **system of linear equations** with the augmented matrix

[A | b] = [a₁  a₂  ⋯  aₙ | b]

#### Theorem: Existence of Solutions

Let A be an m×n matrix. Then the following statements are **equivalent**:

1. For every b in ℝᵐ, the equation Ax = b has a solution.
2. Each b in ℝᵐ is a linear combination of the columns of A.
3. The columns of A span ℝᵐ.
4. A has a pivot position in every row.

### Solution Sets of Linear Systems

#### Homogeneous Systems

The solution set of a homogeneous equation Ax = 0 can always be written as Span{v₁, ..., vₚ} for some vectors v₁, ..., vₚ.

#### Nonhomogeneous Systems

If a nonhomogeneous equation Ax = b (i.e. not setting b to 0 vector) has infinitely many solutions, then the general solution can be written as **one vector plus a linear combination of the vectors spanning the solution set of the corresponding homogeneous equation, Ax = 0**.

To write the general solution in this form, you can use the following general steps:

1. Write the augmented matrix and use row reduction to obtain its reduced echelon form.
2. Write each basic variable in terms of any free variables.
3. Write the solution as a vector x whose entries are in terms of the free variables.
4. Decompose x into a linear combination of vectors: one vector should be constant, and the other vectors should each be a multiple of one of the free variables.

## Module 3: Linear Transformations

### Key Concepts

- One vector → independent only if it’s not zero
- Two vectors → independent only if neither is a scalar multiple of the other
- Any vector that can be built from others → dependence
- More vectors than dimensions → dependence
- Zero vector present → dependence

---



[← Back to Math Fundamentals](./README.md)
