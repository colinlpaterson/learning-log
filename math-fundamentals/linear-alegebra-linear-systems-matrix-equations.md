# Linear Algebra: Linear Systems and Matrix Equations

**Course**: [Linear Algebra: Linear Systems and Matrix Equations](https://www.coursera.org/learn/linear-systems-and-matrix-equations)  
**Platform**: Coursera (John Hopkins University)  
**Started**: January 2026


## Course Overview

Covers matrices, vector and matrix equations, linear transformations

---

## Module 1: Introduction to Matrices

### Key Concepts

#### Row Reduction Echelon Form

- A matrix is in row echelon (steps) form if:
    - All non zero rows are above any rows of all zeros
    - Each leading entry of a row is in a column to the right of the leading entry of the row above it
    - All entries in a column below a leading entry are zero
- A matrix is in row reduced echelon form (rref) if:
    - The first three conditions are met
    - Leading entry in each row is 1
    - Each leading 1 is the only non zero entry in its column
- A pivot position in a matrix is the location corresponding to the leading 1 in rref.
- A pivot column is a column of matrix A that contains a pivot position.
- Key idea: can't see pivots of matrix A unless you convert to ref(A) or rref(A)
- Zero matrix is rref (trivially); 0 pivots
- Theorem 1: A system of linear equations is consistent iff the last (rightmost) colum of its augmened matrix is not a pivot column.
- Theorem 2: A linear system is consistent (at least one solution) iff the right most column of augmented matrix is **not** a pivot column.

---

## Module 2: Vector and Matrix Equations

### Key Concepts

---



[← Back to Math Fundamentals](./README.md)
