# 2. Linear Algebra: Basics

## Matrix Basics

**Matrix addition and subtraction:** If $\mathbf{A} = (a_{ij})$ and $\mathbf{B} = (b_{ij})$ are two $m \times n$ matrices of same dimension, then $\mathbf{A} + \mathbf{B}$ is defined as $(a_{ij} + b_{ij})$. That is, we add element by element the two matrices.  
Clearly $\mathbf{A} + \mathbf{B} = \mathbf{B} + \mathbf{A}$. The rule applies to matrix subtraction.

**Transpose of a matrix:** If $\mathbf{A}$ is an $m \times n$ matrix, then $\mathbf{A}'$ is the $n \times m$ matrix whose rows are the columns of $\mathbf{A}$. So $\mathbf{A}' = (a_{ji})$. For example:

$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}' = \begin{bmatrix}
a & c \\
b & d
\end{bmatrix}
$$

Note: $(\mathbf{A} + \mathbf{B})' = \mathbf{A}' + \mathbf{B}'$, however $(\mathbf{A}\mathbf{B})' = \mathbf{B}'\mathbf{A}'$.

**Null matrix:** Has all elements as 0. Clearly $\mathbf{A} + \mathbf{0}_{m,n} = \mathbf{0}_{m,n} + \mathbf{A} = \mathbf{A}$ for all $m \times n$ matrices.

**Scalar multiplication:** If $\mathbf{A} = (a_{ij})$ then for any constant $k$, define $k\mathbf{A} = (k a_{ij})$. That is, multiply each element in $\mathbf{A}$ by $k$.

**Matrix multiplication:** Say $\mathbf{A}$ is $m \times n$, and $\mathbf{B}$ is $n \times p$, then the $m \times p$ matrix $\mathbf{A}\mathbf{B}$ is the product of $\mathbf{A}$ and $\mathbf{B}$. For example:

$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
\begin{bmatrix}
e & f \\
g & h
\end{bmatrix}
= \begin{bmatrix}
ae + bg & af + bh \\
ce + dg & cf + dh
\end{bmatrix}
$$

and the matrices $\mathbf{A}$ and $\mathbf{B}$ are conformable.

**Diagonal matrix:** A square $n \times n$ matrix $\mathbf{A}$ is diagonal if all entries off the 'main diagonal' are zero, i.e.

$$
\mathbf{A} = \begin{bmatrix}
a_{11} & 0 & \cdots & 0 \\
0 & a_{22} & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & a_{nn}
\end{bmatrix}
$$

Note: The elements in the diagonal of $\mathbf{A}$ are the same as those in $\mathbf{A}'$.

**Trace of a square matrix:** If $\mathbf{A}$ is a square matrix, the trace of $\mathbf{A}$, denoted $\operatorname{tr}(\mathbf{A})$, is the sum of the elements on the main/leading diagonal of $\mathbf{A}$.

**Identity matrix:** Denoted by $\mathbf{I}_n$, the $n \times n$ diagonal matrix with $a_{ii} = 1$ for all $i$. That is:

$$
\mathbf{I}_n = \begin{bmatrix}
1 & 0 & \cdots & 0 \\
0 & 1 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & 1
\end{bmatrix}
$$

**Symmetric matrix:** A square matrix $\mathbf{A}$ is symmetric if $\mathbf{A} = \mathbf{A}'$. The identity matrix and the square null matrix are symmetric.

**Idempotent matrix:** A square matrix is said to be idempotent if $\mathbf{A}^n = \cdots = \mathbf{A}^2 = \mathbf{A}$. Below is an example (try squaring the matrix and see what you get).

$$
\begin{bmatrix}
1 & 0 \\
0 & 0
\end{bmatrix}
$$

**Singular Matrix:** A matrix that is linearly dependent (in the columns or rows) is singular and has determinant of zero. Note that any two (or three) vectors $\mathbf{x}$ and $\mathbf{y}$ (and $\mathbf{z}$) are said to be linearly dependent iff one can be written as a scalar multiple of the other. Two vectors $\mathbf{x} \neq \mathbf{0}$ and $\mathbf{y} \neq \mathbf{0}$ are said to be **linearly independent** iff the ONLY solution to $a\mathbf{x} + b\mathbf{y} = \mathbf{0}$ is $a = 0$ AND $b = 0$. And $\mathbf{x}$ and $\mathbf{y}$ are said to be **orthogonal**.

### Some Notes on Matrices

1. Usually $\mathbf{A}\mathbf{B} \neq \mathbf{B}\mathbf{A}$. For example, try $\mathbf{A} = \begin{bmatrix}2 & 0 \\ 3 & 1\end{bmatrix}$ and $\mathbf{B} = \begin{bmatrix}0 & 1 \\ 0 & 0\end{bmatrix}$.

2. We can have $\mathbf{A}\mathbf{B} = \mathbf{0}$ even if $\mathbf{A}$ or $\mathbf{B}$ are not zero. For example, try $\mathbf{A} = \begin{bmatrix}6 & -12 \\ -3 & 6\end{bmatrix}$ and $\mathbf{B} = \begin{bmatrix}12 & 6 \\ 6 & 3\end{bmatrix}$.

3. Say, $\mathbf{A} = \begin{bmatrix}4 & 8 \\ 1 & 2\end{bmatrix}$, $\mathbf{B} = \begin{bmatrix}2 & 1 \\ 2 & 2\end{bmatrix}$, and $\mathbf{C} = \begin{bmatrix}-2 & 1 \\ 4 & 2\end{bmatrix}$. We find that $\mathbf{A}\mathbf{B} = \mathbf{A}\mathbf{C}$ even though $\mathbf{B} \neq \mathbf{C}$.

4. Say $\mathbf{A}$ and $\mathbf{B}$ are singular matrices. Then $\mathbf{A}\mathbf{B}$ will not be zero, although the product will be a singular matrix.

## Systems of Equations in Matrix Form

One of the uses of linear algebra in economics is to represent and then solve systems of equations. For instance, consider the system of two equations:

$$
3x_1 + 4x_2 = 5 \\
7x_1 - 2x_2 = 2
$$

Here, we can define:

$$
\mathbf{A} = \begin{bmatrix} 3 & 4 \\ 7 & -2 \end{bmatrix}, \quad \mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \end{bmatrix}, \quad \mathbf{b} = \begin{bmatrix} 5 \\ 2 \end{bmatrix}
$$

Then we see that:

$$
\mathbf{A}\mathbf{x} = \begin{bmatrix} 3 & 4 \\ 7 & -2 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} = \begin{bmatrix} 3x_1 + 4x_2 \\ 7x_1 - 2x_2 \end{bmatrix}
$$

The original system is in fact equivalent to the matrix form:

$$
\mathbf{A}\mathbf{x} = \mathbf{b}
$$

## Matrix Inversion

To better understand the mechanics of finding the inverse of a square matrix, let's begin by looking at an example.

$$
\mathbf{A} = \begin{bmatrix} 1 & -2 \\ 3 & 4 \end{bmatrix}
$$

Assume we have:

$$
\begin{bmatrix} a & b \\ c & d \end{bmatrix} = \begin{bmatrix} 4 & 2 \\ -3 & 1 \end{bmatrix}
$$

Where does the 10 in the matrix after the = sign come from? It is the determinant of $\mathbf{A}$.

Now we have:

$$
\begin{bmatrix} 4 & 2 \\ -3 & 1 \end{bmatrix} \begin{bmatrix} 1 & -2 \\ 3 & 4 \end{bmatrix} = \begin{bmatrix} 10 & 0 \\ 0 & 10 \end{bmatrix} = 10 \mathbf{I}
$$

Hence, (pre-)multiplying both sides of the equation by $\frac{1}{10}$ will give you:

$$
\frac{1}{10} \begin{bmatrix} 4 & 2 \\ -3 & 1 \end{bmatrix} \begin{bmatrix} 1 & -2 \\ 3 & 4 \end{bmatrix} = \mathbf{I}
$$

The matrix $\frac{1}{10} \begin{bmatrix} 4 & 2 \\ -3 & 1 \end{bmatrix}$ is in fact the inverse of $\mathbf{A}$. Hence we have the relationship $\mathbf{A}\mathbf{A}^{-1} = \mathbf{I}$. In fact, $\mathbf{A}^{-1}\mathbf{A} = \mathbf{A}\mathbf{A}^{-1} = \mathbf{I}$.

### Properties of Inverse

Here are some properties of the inverse of a matrix worth knowing:

**Property 1:** For any nonsingular matrix $\mathbf{A}$, $(\mathbf{A}^{-1})^{-1} = \mathbf{A}$.

**Property 2:** The determinant of the inverse of a matrix is equal to the reciprocal of the determinant of the matrix. That is $|\mathbf{A}^{-1}| = \frac{1}{|\mathbf{A}|}$.

**Property 3:** The inverse of matrix $\mathbf{A}$ is unique.

**Property 4:** For any nonsingular matrix $\mathbf{A}$, the inverse of the transpose of a matrix is equal to the transpose of the inverse of the matrix. $(\mathbf{A}')^{-1} = (\mathbf{A}^{-1})'$.

**Property 5:** If $\mathbf{A}$ and $\mathbf{B}$ are nonsingular and of the same dimension, then $\mathbf{A}\mathbf{B}$ is also nonsingular.

**Property 6:** The inverse of the product of two matrices is equal to the product of their inverses in reverse order. $(\mathbf{A}\mathbf{B})^{-1} = \mathbf{B}^{-1}\mathbf{A}^{-1}$.

## The Determinant of a Matrix

The determinant is a scalar value uniquely associated with a square non-singular matrix, and is usually denoted as $|\mathbf{A}|$. The question of whether or not a matrix is nonsingular and therefore invertible is linked to the value of its determinant.

We can write a generic $2 \times 2$ matrix as:

$$
\mathbf{A} = \begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{bmatrix}
$$

and its determinant is defined as:

$$
|\mathbf{A}| = a_{11}a_{22} - a_{12}a_{21}
$$

For a $3 \times 3$ matrix, say:

$$
\mathbf{B} = \begin{bmatrix} b_{11} & b_{12} & b_{13} \\ b_{21} & b_{22} & b_{23} \\ b_{31} & b_{32} & b_{33} \end{bmatrix}
$$

its determinant is:

$$
|\mathbf{B}| = b_{11}(b_{22}b_{33} - b_{23}b_{32}) - b_{12}(b_{21}b_{33} - b_{23}b_{31}) + b_{13}(b_{21}b_{32} - b_{22}b_{31})
$$

### Properties of Determinants

**Property 1:** $|\mathbf{A}| = |\mathbf{A}'|$ and $|\mathbf{A}| \cdot |\mathbf{B}| = |\mathbf{B}| \cdot |\mathbf{A}|$.

**Property 2:** Interchanging any two rows or columns will affect the sign of the determinant, but not its absolute value.

**Property 3:** Multiplying a single row or column by a scalar will cause the value of the determinant to be multiplied by the scalar.

**Property 4:** Addition or subtraction of a nonzero multiple of any row or column to or from another row or column does not change the value of the determinant.

**Property 5:** The determinant of a triangular matrix is equal to the product of the elements along the principal diagonal.

**Property 6:** If any of the rows or columns equal zero, the determinant is also zero.

**Property 7:** If two rows or columns are identical or proportional, i.e. linearly dependent, then the determinant is zero.

## Finding the Inverse of a Matrix

The inverse of a matrix is defined as:

$$
\mathbf{A}^{-1} = \frac{1}{|\mathbf{A}|} \operatorname{adj}(\mathbf{A})
$$

Let's say we have the following linear system:

$$
2x_1 + 9x_2 + 4x_3 = -13 \\
7x_1 - 8x_2 + 6x_3 = 63 \\
5x_1 + 3x_2 - 6x_3 = 6
$$

Writing the above system in the form $\mathbf{A}\mathbf{x} = \mathbf{b}$, where:

$$
\mathbf{A} = \begin{bmatrix} 2 & 9 & 4 \\ 7 & -8 & 6 \\ 5 & 3 & -6 \end{bmatrix}, \quad \mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix}, \quad \mathbf{b} = \begin{bmatrix} -13 \\ 63 \\ 6 \end{bmatrix}
$$

We can therefore solve the system by $\mathbf{x} = \mathbf{A}^{-1}\mathbf{b}$, which means that we need the inverse of $\mathbf{A}$.

**Step 1.** The minor $|M_{ij}|$ is the determinant of the submatrix formed by deleting the $i$-th row and $j$-th column of the original matrix. So we have:

$$
\begin{bmatrix}
30 & -72 & 61 \\
-66 & -32 & -39 \\
86 & -16 & -79
\end{bmatrix}
$$

**Step 2:** The cofactor $C_{ij}$ is a minor with the prescribed sign that follows the rule:

$$
C_{ij} = (-1)^{i+j} |M_{ij}|
$$

Hence, we have:

$$
\begin{bmatrix}
30 & 72 & 61 \\
66 & -32 & 39 \\
86 & 16 & -79
\end{bmatrix}
$$

**Step 3:** An adjoint matrix is simply the transpose of a cofactor matrix. Continuing the example above, we have:

$$
\operatorname{adj}(\mathbf{A}) = \begin{bmatrix}
30 & 66 & 86 \\
72 & -32 & 16 \\
61 & 39 & -79
\end{bmatrix}
$$

Since $|\mathbf{A}| = 952$, we then have:

$$
\mathbf{A}^{-1} = \frac{1}{952} \begin{bmatrix}
30 & 66 & 86 \\
72 & -32 & 16 \\
61 & 39 & -79
\end{bmatrix}
$$

and

$$
\mathbf{x} = \mathbf{A}^{-1}\mathbf{b} = \frac{1}{952} \begin{bmatrix}
30 & 66 & 86 \\
72 & -32 & 16 \\
61 & 39 & -79
\end{bmatrix} \begin{bmatrix} -13 \\ 63 \\ 6 \end{bmatrix}
$$

Not a nice one to solve, though.

## Cramer's Rule

Cramer came up with a simplified method for solving a system of linear equations through the use of determinants.

Basically, given $\mathbf{A}\mathbf{x} = \mathbf{b}$, we have:

$$
\mathbf{A} = \begin{bmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{bmatrix}, \quad \mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix}, \quad \mathbf{b} = \begin{bmatrix} b_1 \\ b_2 \\ b_3 \end{bmatrix}
$$

Define:

$$
\Delta = |\mathbf{A}|
$$

and

$$
\Delta_1 = \begin{vmatrix} b_1 & a_{12} & a_{13} \\ b_2 & a_{22} & a_{23} \\ b_3 & a_{32} & a_{33} \end{vmatrix}, \quad \Delta_2 = \begin{vmatrix} a_{11} & b_1 & a_{13} \\ a_{21} & b_2 & a_{23} \\ a_{31} & b_3 & a_{33} \end{vmatrix}, \quad \Delta_3 = \begin{vmatrix} a_{11} & a_{12} & b_1 \\ a_{21} & a_{22} & b_2 \\ a_{31} & a_{32} & b_3 \end{vmatrix}
$$

where the columns in the $\mathbf{A}$ matrix are replaced one by one by the $\mathbf{b}$ vector as shown above.

Then:

$$
x_i = \frac{\Delta_i}{\Delta}
$$

Verify that you get $\{4.5, -3, 1.25\}$.

---
*Linear algebra 1-5.pptx (17107k) 8 Jan 31, 2018, 7:56 AM v.1*  
*Linear algebra 6.pptx (3924k) 8 Feb 5, 2018, 7:15 AM v.1*