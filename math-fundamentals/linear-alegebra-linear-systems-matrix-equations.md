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
- A solution of a system of linear equations is the set of point that make every equation in the system true.
- Solutions of linear systems correspond to how lines can meet
  - 3 ways lines can meet:
    - 1 solution, 0 solution, inf solutions
- A linear system is consistent if either 1 or inf solutions exist
- Equivalent linear systems have the same solution set
- 3 elementary row operations (ERO)
  - Replacement: replace one row by the sum of itself and multiple of another row
  - Interchange: swap position of 2 rows
  - Scaling: multiply all entries in a row by a non-zero constant
- Two matrics are row-equivalent if there is a sequence of EROs that transforms one into another
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

**Key idea**: can't see pivots of matrix A unless you convert to ref(A) or rref(A)
- Zero matrix is rref (trivially); 0 pivots
- **Theorem**: A system of linear equations is consistent iff the last (rightmost) colum of its augmened matrix is not a pivot column.

---

## Module 2: Vector and Matrix Equations

### Key Concepts

---



[← Back to Math Fundamentals](./README.md)
