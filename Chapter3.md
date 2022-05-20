# Chapter-3 : Linear Algebra- Review

## Matrices:
It is a 2D array.<br>
A(i,j): where i is the row and j is the column of the matrix.<br>
The size of the matrix can be defined as the (number of rows) X (number of columns)

## Vector:
It is an (n X 1) matrix  i.e n rows an done column.

## Matrix Manipulation:
### Addition: 
+ Only adds matrices of the same dimension.
+ Adds elements one at a time
+ It generates the matrix that is of the same size as the original matrix.

### Multiplication or Division by Scalar:
+ Multiplies or divides each element by the scalar.
+ It generates the matrix that is of the same size as the original matrix.

### Matrix by vector multiplication: 
+ When multiplying a matrix with the vector then, the matrix A's colunms size should be the same as the  matrix B's rows size.
+ It generates the matrix of A's rows X B's columns size.

### Matrix Multiplication properties:
+ Matrix is associative i.e A + B = B + A
+ Matrix is not commutative i.e A x B != B x A


### Identity Matrix: 
+ A matrix that has all 1's in the diagonal and the rest as 0's

## Inverse Matrix:
+ An inverse matrix is the inverse of the original matrix i.e 1/matrix := (matrix)^(-1)
+ The multiplication of the original matrix and the inverse matrix gives the identity matrix.
+ Only matrices that has a dimension of m X m (squared matrices) has inverses.
 
## Transpose Matrix:
Obtaining a matrix by switching the rows into columns and the cloumns into the rows.