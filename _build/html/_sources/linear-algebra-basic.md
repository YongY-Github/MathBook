# 2. Linear Algebra: Basics

This chapter introduces the basic algebraic objects and operations that underpin
most of applied mathematics in economics, statistics, and optimization.
The emphasis is on **mechanics**, **intuition**, and **practical manipulation**,
rather than abstract proofs.

---

## Matrix Basics

### Matrix Addition and Subtraction

If
$\mathbf{A} = (a_{ij})$ and $\mathbf{B} = (b_{ij})$
are two $m \times n$ matrices of the same dimension, then matrix addition is defined element by element:

$$
\mathbf{A} + \mathbf{B} = (a_{ij} + b_{ij}).
$$

That is, we add the corresponding elements of the two matrices.

Clearly,
$$
\mathbf{A} + \mathbf{B} = \mathbf{B} + \mathbf{A}.
$$

The same rule applies to matrix subtraction.

---

### Transpose of a Matrix

If $\mathbf{A}$ is an $m \times n$ matrix, then $\mathbf{A}'$ is the $n \times m$ matrix whose rows are the columns of $\mathbf{A}$. Formally,

$$
\mathbf{A}' = (a_{ji}).
$$

**Example:**
$$
\begin{bmatrix}
a & b \
c & d
\end{bmatrix}'
==============

\begin{bmatrix}
a & c \
b & d
\end{bmatrix}.
$$

The transpose interacts nicely with addition, but not with multiplication:

* $(\mathbf{A} + \mathbf{B})' = \mathbf{A}' + \mathbf{B}'$
* $(\mathbf{A}\mathbf{B})' = \mathbf{B}'\mathbf{A}'$

---

### Null (Zero) Matrix

The **null matrix** has all elements equal to zero.

For any $m \times n$ matrix $\mathbf{A}$,
$$
\mathbf{A} + \mathbf{0}*{m,n} = \mathbf{0}*{m,n} + \mathbf{A} = \mathbf{A}.
$$

---

### Scalar Multiplication

If $\mathbf{A} = (a_{ij})$ and $k$ is a scalar, define

$$
k\mathbf{A} = (k a_{ij}),
$$

that is, multiply every element of $\mathbf{A}$ by $k$.

---

### Matrix Multiplication

Suppose $\mathbf{A}$ is $m \times n$ and $\mathbf{B}$ is $n \times p$.
Then the product $\mathbf{A}\mathbf{B}$ is an $m \times p$ matrix.

**Example:**
$$
\begin{bmatrix}
a & b \
c & d
\end{bmatrix}
\begin{bmatrix}
e & f \
g & h
\end{bmatrix}
=============

\begin{bmatrix}
ae + bg & af + bh \
ce + dg & cf + dh
\end{bmatrix}.
$$

The matrices $\mathbf{A}$ and $\mathbf{B}$ are said to be **conformable**.

Matrix multiplication is generally **not commutative**:
$\mathbf{A}\mathbf{B} \neq \mathbf{B}\mathbf{A}$.

---

### Diagonal Matrix

A square $n \times n$ matrix $\mathbf{A}$ is **diagonal** if all off-diagonal elements are zero:

$$
\mathbf{A} =
\begin{bmatrix}
a_{11} & 0 & \cdots & 0 \
0 & a_{22} & \cdots & 0 \
\vdots & \vdots & \ddots & \vdots \
0 & 0 & \cdots & a_{nn}
\end{bmatrix}.
$$

The diagonal elements of $\mathbf{A}$ are the same as those of $\mathbf{A}'$.

---

### Trace of a Square Matrix

For a square matrix $\mathbf{A}$, the **trace**, denoted $\operatorname{tr}(\mathbf{A})$, is the sum of the elements on the main diagonal.

---

### Identity Matrix

The **identity matrix** $\mathbf{I}_n$ is the $n \times n$ diagonal matrix with ones on the diagonal:

$$
\mathbf{I}_n =
\begin{bmatrix}
1 & 0 & \cdots & 0 \
0 & 1 & \cdots & 0 \
\vdots & \vdots & \ddots & \vdots \
0 & 0 & \cdots & 1
\end{bmatrix}.
$$

---

### Symmetric Matrix

A square matrix $\mathbf{A}$ is **symmetric** if

$$
\mathbf{A} = \mathbf{A}'.
$$

The identity matrix and the square null matrix are symmetric.

---

## Idempotent Matrix

A square matrix is **idempotent** if

$$
\mathbf{A}^2 = \mathbf{A}.
$$

Try squaring the following matrix:
$$
\begin{bmatrix}
1 & 0 \
0 & 0
\end{bmatrix}.
$$

---

## Singular Matrix and Linear Dependence

A matrix is **singular** if its rows or columns are linearly dependent.
A singular matrix has determinant zero.

Two vectors $\mathbf{x}$ and $\mathbf{y}$ are **linearly dependent** if one can be written as a scalar multiple of the other.

They are **linearly independent** if the only solution to

$$
a\mathbf{x} + b\mathbf{y} = \mathbf{0}
$$

is $a = 0$ and $b = 0$.

Two nonzero vectors are **orthogonal** if their inner product is zero.

---

## Some Notes on Matrices

1. In general, $\mathbf{A}\mathbf{B} \neq \mathbf{B}\mathbf{A}$.
   Try $\mathbf{A} = \begin{bmatrix}2 & 0 \ 3 & 1\end{bmatrix}$ and
   $\mathbf{B} = \begin{bmatrix}0 & 1 \ 0 & 0\end{bmatrix}$.

2. It is possible that $\mathbf{A}\mathbf{B} = \mathbf{0}$ even if neither $\mathbf{A}$ nor $\mathbf{B}$ is zero.
   Try
   $$
   \mathbf{A} =
   \begin{bmatrix}6 & -12 \ -3 & 6\end{bmatrix},
   \quad
   \mathbf{B} =
   \begin{bmatrix}12 & 6 \ 6 & 3\end{bmatrix}.
   $$

3. We can have $\mathbf{A}\mathbf{B} = \mathbf{A}\mathbf{C}$ even if $\mathbf{B} \neq \mathbf{C}$.
   Example matrices are given below.

4. If $\mathbf{A}$ and $\mathbf{B}$ are singular, then $\mathbf{A}\mathbf{B}$ is also singular, though not necessarily zero.

---

## Systems of Equations in Matrix Form

Consider the system:
$$
\begin{aligned}
3x_1 + 4x_2 &= 5 \
7x_1 - 2x_2 &= 2
\end{aligned}
$$

Define:
$$
\mathbf{A} =
\begin{pmatrix} 3 & 4 \ 7 & -2 \end{pmatrix},
\quad
\mathbf{x} =
\begin{pmatrix} x_1 \ x_2 \end{pmatrix},
\quad
\mathbf{b} =
\begin{pmatrix} 5 \ 2 \end{pmatrix}.
$$

Then the system can be written compactly as:
$$
\mathbf{A}\mathbf{x} = \mathbf{b}.
$$

---

## Matrix Inversion

Consider:
$$
\mathbf{A} =
\begin{bmatrix} 1 & -2 \ 3 & 4 \end{bmatrix}.
$$

Suppose
$$
\begin{bmatrix} a & b \ c & d \end{bmatrix}
===========================================

\begin{bmatrix} 4 & 2 \ -3 & 1 \end{bmatrix}.
$$

The number 10 that appears below is the **determinant** of $\mathbf{A}$.

$$
\begin{bmatrix} 4 & 2 \ -3 & 1 \end{bmatrix}
\begin{bmatrix} 1 & -2 \ 3 & 4 \end{bmatrix}
============================================

# \begin{bmatrix} 10 & 0 \ 0 & 10 \end{bmatrix}

10\mathbf{I}.
$$

Multiplying both sides by $\frac{1}{10}$ gives:
$$
\frac{1}{10}
\begin{bmatrix} 4 & 2 \ -3 & 1 \end{bmatrix}
\begin{bmatrix} 1 & -2 \ 3 & 4 \end{bmatrix}
============================================

\mathbf{I}.
$$

Thus,
$$
\mathbf{A}^{-1}
===============

\frac{1}{10}
\begin{bmatrix} 4 & 2 \ -3 & 1 \end{bmatrix}.
$$

---

## Determinant of a Matrix

For a $2 \times 2$ matrix:
$$
\mathbf{A} =
\begin{bmatrix}
a_{11} & a_{12} \
a_{21} & a_{22}
\end{bmatrix},
$$

the determinant is:
$$
|\mathbf{A}| = a_{11}a_{22} - a_{12}a_{21}.
$$

The $3 \times 3$ case follows analogously (formula retained exactly as given).

---

## Cramer’s Rule

Given $\mathbf{A}\mathbf{x} = \mathbf{b}$, define:
$$
\Delta = |\mathbf{A}|, \qquad x_i = \frac{\Delta_i}{\Delta}.
$$

Verify that the solution is ${4.5, -3, 1.25}$.

---

Linear algebra 1–5.pptx (2018)
Linear algebra 6.pptx (2018)

---
