# 3. Linear Algebra: Special Matrices

Let's look at some special matrices and determinants that are useful in economic analysis.

## The Jacobian

The Jacobian (named after German mathematician Karl Gustav Jacobi, 1804–1851) is generally used in conjunction with partial derivatives to provide an easy test for the existence of functional dependence (linear and nonlinear). A Jacobian determinant $|\mathbf{J}|$ is composed of all the first‑order partial derivatives of a system of equations, arranged in order sequence. Given

$$
y_{1} = f_{1}(x_{1},x_{2},x_{3}) \\
y_{2} = f_{2}(x_{1},x_{2},x_{3}) \\
y_{3} = f_{3}(x_{1},x_{2},x_{3})
$$

Then

$$
|\mathbf{J}| = 
\begin{vmatrix}
\frac{\partial y_{1}}{\partial x_{1}} & \frac{\partial y_{1}}{\partial x_{2}} & \frac{\partial y_{1}}{\partial x_{3}} \\[4pt]
\frac{\partial y_{2}}{\partial x_{1}} & \frac{\partial y_{2}}{\partial x_{2}} & \frac{\partial y_{2}}{\partial x_{3}} \\[4pt]
\frac{\partial y_{3}}{\partial x_{1}} & \frac{\partial y_{3}}{\partial x_{2}} & \frac{\partial y_{3}}{\partial x_{3}}
\end{vmatrix}
$$

For example, say you have

$$
y_{1} = 5x_{1} + 3x_{2} \\
y_{2} = 25x_{1}^{2} + 30x_{1}x_{2} + 9x_{2}^{2}
$$

Then taking the first‑order partials gives

$$
\frac{\partial y_1}{\partial x_1} = 5,\qquad 
\frac{\partial y_1}{\partial x_2} = 3,\qquad 
\frac{\partial y_2}{\partial x_1} = 50x_1 + 30x_2,\qquad 
\frac{\partial y_2}{\partial x_2} = 30x_1 + 18x_2
$$

And the Jacobian is

$$
|\mathbf{J}| = 
\begin{vmatrix}
5 & 3 \\
50x_1 + 30x_2 & 30x_1 + 18x_2
\end{vmatrix}
$$

The determinant of the Jacobian matrix is

$$
|\mathbf{J}| = 5(30x_1 + 18x_2) - 3(50x_1 + 30x_2) = 0
$$

Since $|\mathbf{J}| = 0$, there is functional dependence between the equations. (Note: $(5x_{1} + 3x_{2})^{2} = 25x_{1}^{2} + 30x_{1}x_{2} + 9x_{2}^{2}$.)

## The Hessian

Given that the first‑order conditions $z_{x} = z_{y} = 0$ are met, a sufficient condition for a multivariate function $z = f(x,y)$ to be an optimum is

1. $z_{xx}, z_{yy} > 0$ for a minimum; $z_{xx}, z_{yy} < 0$ for a maximum.
2. $z_{xx} z_{yy} > (z_{xy})^{2}$.

A convenient test for this second‑order condition is provided by the Hessian. A Hessian $|\mathbf{H}|$ is a determinant composed of all the second‑order partial derivatives, with the second‑order direct partials on the principal diagonal and the second‑order cross partials off the principal diagonal. That is,

$$
|\mathbf{H}| = 
\begin{vmatrix}
z_{xx} & z_{xy} \\
z_{yx} & z_{yy}
\end{vmatrix}
$$

where (by Young's Theorem) $z_{xy} = z_{yx}$.

If the first element on the principal diagonal, a.k.a. the first principal minor, $|H_{1}| = z_{xx}$ is positive, and the second principal minor

$$
|H_{2}| = 
\begin{vmatrix}
z_{xx} & z_{xy} \\
z_{yx} & z_{yy}
\end{vmatrix}
= z_{xx} z_{yy} - (z_{xy})^{2} > 0,
$$

then the second‑order conditions for a minimum are set. That is, when $|H_{1}| > 0$ and $|H_{2}| > 0$, the Hessian $|\mathbf{H}|$ is said to be **positive definite**. And a positive definite Hessian fulfills the second‑order conditions for a minimum.

If the first principal minor $|H_{1}| < 0$, while the second principal minor remains positive, then the second‑order conditions for a maximum are met. That is, when $|H_{1}| < 0$ and $|H_{2}| > 0$, the Hessian $|\mathbf{H}|$ is said to be **negative definite** and fulfills the second‑order conditions for a maximum.

Let's take an example:

Given

$$
z = f(x,y) = 2x^{2} - xy + 2y^{2} - 5x - 6y + 20,
$$

then

$$
z_x = 4x - y - 5,\quad z_y = -x + 4y - 6,\quad z_{xx} = 4,\quad z_{yy} = 4,\quad z_{xy} = z_{yx} = -1.
$$

The Hessian is

$$
|\mathbf{H}| = 
\begin{vmatrix}
4 & -1 \\
-1 & 4
\end{vmatrix}
$$

We have $|H_{1}| = 4 > 0$ and $|H_{2}| = (4)(4) - (-1)^2 = 16 - 1 = 15 > 0$. Since $|H_{1}| > 0$ and $|H_{2}| > 0$, i.e. the Hessian is positive definite, then the function $z$ is characterized by a minimum at the critical values (can you find these?).

## The Discriminant

Determinants can be used to test for positive and negative definiteness of any quadratic form. The determinant of a quadratic form is called a **discriminant** $|\mathbf{D}|$. Given the quadratic form

$$
z = a x^{2} + b x y + c y^{2},
$$

the determinant is formed by placing the coefficients of the squared terms on the principal diagonal and dividing the coefficients of the non‑squared terms equally between the off‑diagonal positions. Hence, we have

$$
|\mathbf{D}| = 
\begin{vmatrix}
a & b/2 \\
b/2 & c
\end{vmatrix}
$$

We then evaluate the principal minors like we did for the Hessian test, where

$$
|D_{1}| = a \quad \text{and} \quad |D_{2}| = 
\begin{vmatrix}
a & b/2 \\
b/2 & c
\end{vmatrix}
= a c - \frac{b^{2}}{4}.
$$

If $|D_{1}|, |D_{2}| > 0$, $|\mathbf{D}|$ is positive definite and $z$ is positive for all nonzero values of $x$ and $y$. If $|D_{1}| < 0$ and $|D_{2}| > 0$, $|\mathbf{D}|$ is negative definite and $z$ is negative for all nonzero values of $x$ and $y$. If $|D_{2}| \neq 0$, $z$ is not sign definite and $z$ may assume both positive and negative values.

Let's take an example to test for sign definiteness of the following quadratic form

$$
z = 2x^{2} + 5xy + 8y^{2}.
$$

We can easily form the discriminant

$$
|\mathbf{D}| = 
\begin{vmatrix}
2 & 2.5 \\
2.5 & 8
\end{vmatrix}
$$

Then evaluating the principal minors gives

$$
|D_{1}| = 2 > 0, \qquad |D_{2}| = 
\begin{vmatrix}
2 & 2.5 \\
2.5 & 8
\end{vmatrix}
= 16 - 6.25 = 9.75 > 0.
$$

Hence, $z$ is positive definite, meaning that it will be greater than zero for all nonzero values of $x$ and $y$.

## The Quadratic Form

A quadratic form is defined as a polynomial expression in which each component term has a uniform degree.

Here are some examples:

$$
6x^{2} - 2xy + 3y^{2} \quad \text{is a quadratic form in 2 variables.} \\
x^{2} + 2xy + 4xz + 2yz + y^{2} + z^{2} \quad \text{is a quadratic form in 3 variables.}
$$

It would be useful to determine the sign definiteness so we can make statements concerning the optimum value of the function as to whether it is a minimum or a maximum.

More generally, a quadratic form in $n$ variables $(x_{1},x_{2},\ldots ,x_{n})$ can be written as $\mathbf{x}^{\prime}\mathbf{A}\mathbf{x}$ where

$\mathbf{x}^{\prime}$ is a row vector $[x_{1},x_{2},\dots,x_{n}]$ and  
$\mathbf{A}$ is an $n\times n$ matrix of scalar elements.

To see this more clearly,

$$
\mathbf{x}^{\prime}\mathbf{A}\mathbf{x} = 
\begin{bmatrix}
x_{1} & x_{2}
\end{bmatrix}
\begin{bmatrix}
1 & 3 \\
4 & 5
\end{bmatrix}
\begin{bmatrix}
x_{1} \\
x_{2}
\end{bmatrix}
= 
\begin{bmatrix}
x_{1} + 4x_{2} & 3x_{1} + 5x_{2}
\end{bmatrix}
\begin{bmatrix}
x_{1} \\
x_{2}
\end{bmatrix}
= x_{1}^{2} + 7x_{1}x_{2} + 5x_{2}^{2}.
$$

A quadratic form is said to be:

a) **Positive definite** if $\mathbf{x}^{\prime}\mathbf{A}\mathbf{x} > 0$ for all $\mathbf{x} \neq \mathbf{0}$.  
b) **Positive semi‑definite** if $\mathbf{x}^{\prime}\mathbf{A}\mathbf{x} \geq 0$ and $\exists \mathbf{x} \neq \mathbf{0}$ such that $\mathbf{x}^{\prime}\mathbf{A}\mathbf{x} = 0$.  
c) **Negative definite** if $\mathbf{x}^{\prime}\mathbf{A}\mathbf{x} < 0$ for all $\mathbf{x} \neq \mathbf{0}$.  
d) **Negative semi‑definite** if $\mathbf{x}^{\prime}\mathbf{A}\mathbf{x} \leq 0$ and $\exists \mathbf{x} \neq \mathbf{0}$ such that $\mathbf{x}^{\prime}\mathbf{A}\mathbf{x} = 0$.  
e) **Sign indefinite** if it takes both positive and negative values.

Quadratic forms are particularly useful in determining the concavity or convexity of a differentiable function.

For a function $y = f(x_{1},x_{2},\dots,x_{n})$, we can form the Hessian consisting of second‑order partial derivatives and construct a quadratic form as $\mathbf{x}^{\prime}\mathbf{H}\mathbf{x}$. Then

a) The function $y$ is strictly convex if the quadratic form is positive (implying that the Hessian is positive definite, i.e., the determinants of the principal minors are all positive).  
b) The function $y$ is strictly concave if the quadratic form is negative (that is, the Hessian is negative definite, i.e. the determinants of the principal minors alternate in sign).

Let's take an example to see this more clearly.

Say we have

$$
z = x^{2} + y^{2}.
$$

Then

$$
z_{x} = 2x,\quad z_{xx} = 2,\quad z_{xy} = 0, \\
z_{y} = 2y,\quad z_{yx} = 0,\quad z_{yy} = 2.
$$

But

$$
\mathbf{x}^{\prime}\mathbf{H}\mathbf{x} = z_{xx}x^{2} + z_{yy}y^{2} + z_{xy}z_{yx}xy = 2x^{2} + 2y^{2} > 0.
$$

Hence the function $z = x^{2} + y^{2}$ is characterized by a minimum at its optimal value and is therefore a strictly convex function. And it is easy to see that the Hessian is positive definite!

Here's another example:

Say we have a quadratic form in 2 variables

$$
z = 8x^{2} + 6xy + 2y^{2}.
$$

This can be rearranged as

$$
z = 8x^{2} + 3xy + 3xy + 2y^{2}.
$$

We can write this as

$$
\mathbf{x}^{\prime}\mathbf{H}\mathbf{x} = z_{xx}x^{2} + z_{yy}y^{2} + z_{xy}z_{yx}xy = 8x^{2} + 2y^{2} + (3)(3)xy = 8x^{2} + 2y^{2} + 9xy.
$$

The Hessian is

$$
\mathbf{H} = 
\begin{bmatrix}
8 & 3 \\
3 & 2
\end{bmatrix}
$$

The principal minors are $|H_{1}| = 8$ and $|H_{2}| = 
\begin{vmatrix}
8 & 3 \\
3 & 2
\end{vmatrix} = 16 - 9 = 7.$

Both are positive so we have the Hessian and the quadratic form as positive definite.

## Higher Order Hessian

Given $y = f(x_{1},x_{2},x_{3})$, the third‑order Hessian is

$$
|\mathbf{H}| = 
\begin{vmatrix}
y_{11} & y_{12} & y_{13} \\
y_{21} & y_{22} & y_{23} \\
y_{31} & y_{32} & y_{33}
\end{vmatrix}
$$

where the elements are the various second‑order partial derivatives of $y$:

$$
y_{11} = \frac{\partial^{2}y}{\partial x_{1}^{2}},\quad 
y_{12} = \frac{\partial^{2}y}{\partial x_{2}\partial x_{1}},\quad 
y_{23} = \frac{\partial^{2}y}{\partial x_{3}\partial x_{2}},\quad \text{etc.}
$$

Conditions for a relative minimum or maximum depend on the signs of the first, second, and third principal minors, respectively. If

$$
|H_{1}| > 0,\quad 
|H_{2}| = 
\begin{vmatrix}
y_{11} & y_{12} \\
y_{21} & y_{22}
\end{vmatrix} > 0,\quad 
\text{and} \quad |H_{3}| = |\mathbf{H}| > 0,
$$

then $|\mathbf{H}|$ is positive definite and fulfills the second‑order conditions for a minimum.

If

$$
|H_{1}| < 0,\quad 
|H_{2}| = 
\begin{vmatrix}
y_{11} & y_{12} \\
y_{21} & y_{22}
\end{vmatrix} > 0,\quad 
\text{and} \quad |H_{3}| = |\mathbf{H}| < 0,
$$

then $|\mathbf{H}|$ is negative definite and fulfills the second‑order conditions for a maximum.

Let's take an example.

Given the function

$$
y = -5x_{1}^{2} + 10x_{1} + x_{1}x_{3} - 2x_{2}^{2} + 4x_{2} + 2x_{2}x_{3} - 4x_{3}^{2}.
$$

The first order conditions (F.O.C) are

$$
\frac{\partial y}{\partial x_1} = y_1 = -10x_1 + 10 + x_3 = 0, \\
\frac{\partial y}{\partial x_2} = y_2 = -4x_2 + 2x_3 + 4 = 0, \\
\frac{\partial y}{\partial x_3} = y_3 = x_1 + 2x_2 - 8x_3 = 0.
$$

which can be expressed in matrix form as

$$
\begin{bmatrix}
-10 & 0 & 1 \\
0 & -4 & 2 \\
1 & 2 & -8
\end{bmatrix}
\begin{bmatrix}
x_1 \\ x_2 \\ x_3
\end{bmatrix}
= 
\begin{bmatrix}
-10 \\ -4 \\ 0
\end{bmatrix}.
$$

Using Cramer's rule we get $x_1 \approx 1.04$, $x_2 \approx 1.22$ and $x_3 \approx 0.43$ (please verify this).

Let's take the second partial derivatives from the first‑order conditions to create the Hessian,

$$
y_{11} = -10,\quad y_{12} = 0,\quad y_{13} = 1, \\
y_{21} = 0,\quad y_{22} = -4,\quad y_{23} = 2, \\
y_{31} = 1,\quad y_{32} = 2,\quad y_{33} = -8.
$$

Thus,

$$
\mathbf{H} = 
\begin{bmatrix}
-10 & 0 & 1 \\
0 & -4 & 2 \\
1 & 2 & -8
\end{bmatrix}
$$

Finally, applying the Hessian test, we have

$$
|H_1| = -10 < 0,\quad 
|H_2| = 
\begin{vmatrix}
-10 & 0 \\
0 & -4
\end{vmatrix} = 40 > 0,\quad 
|H_3| = |\mathbf{H}| = 
\begin{vmatrix}
-10 & 0 & 1 \\
0 & -4 & 2 \\
1 & 2 & -8
\end{vmatrix} = -80 < 0.
$$

Since the principal minors alternate correctly in sign, the Hessian is negative definite and the function is maximized at $x_1 \approx 1.04$, $x_2 \approx 1.22$ and $x_3 \approx 0.43$.

## The Bordered Hessian

To optimize a function $f(x_1, x_2)$ subject to a constraint $g(x_1, x_2)$ the first‑order conditions can be found by setting up what is known as the Lagrangian function $F(x_1, x_2, \lambda) = f(x_1, x_2) - \lambda(g(x_1, x_2) - c)$.

The second‑order conditions can be expressed in terms of a bordered Hessian $|\bar{\mathbf{H}}|$ as

$$
|\bar{\mathbf{H}}| = 
\begin{vmatrix}
0 & g_1 & g_2 \\
g_1 & F_{11} & F_{12} \\
g_2 & F_{21} & F_{22}
\end{vmatrix}
$$

or

$$
|\bar{\mathbf{H}}| = 
\begin{vmatrix}
0 & g_1 & g_2 \\
g_1 & f_{11} & f_{12} \\
g_2 & f_{21} & f_{22}
\end{vmatrix}
$$

which is the usual Hessian bordered by the first derivatives of the constraint with zero on the principal diagonal.

The order of a bordered principal minor is determined by the order of the principal minor being bordered. Hence $|\bar{H}_2|$ above represents a second bordered principal minor, because the principal minor being bordered has dimensions $2\times 2$.

For the bivariate case with a single constraint, we simply look at $|\bar{H}_2|$. If this is negative, the bordered Hessian is said to be positive definite and satisfies the second‑order condition for a minimum. However, if it is positive, the bordered Hessian is said to be negative definite, and meets the sufficient conditions for a maximum.

Let's try optimizing the following objective function

$$
f(x_1, x_2) = 4x_1^2 + 3x_2^2 - 2x_1x_2
$$

subject to

$$
x_1 + x_2 = 56.
$$

Setting up the Lagrangian function, taking the first‑order partials and solving gives $x_1^* = 36$, $x_2^* = 20$ (and $\lambda = 348$). (You should verify this.)

The bordered Hessian for this optimization problem is

$$
|\bar{\mathbf{H}}| = 
\begin{vmatrix}
0 & 1 & 1 \\
1 & 8 & -2 \\
1 & -2 & 6
\end{vmatrix}
$$

Starting with the second principal minor, we have

$$
|\bar{H}_2| = |\bar{\mathbf{H}}| = 0 \cdot 
\begin{vmatrix}
8 & -2 \\
-2 & 6
\end{vmatrix}
- 1 \cdot 
\begin{vmatrix}
1 & -2 \\
1 & 6
\end{vmatrix}
+ 1 \cdot 
\begin{vmatrix}
1 & 8 \\
1 & -2
\end{vmatrix}
= - (6+2) + (-2-8) = -8 -10 = -18.
$$

which is negative, hence $|\bar{\mathbf{H}}|$ is positive definite and we have met sufficient conditions for a minimum.

For the more general case in which the objective function has say $n$ variables, i.e., $f(x_1, \ldots , x_n)$ which is subject to some constraint $g(x_1, \ldots , x_n)$, we can set up the bordered Hessian as

$$
|\bar{\mathbf{H}}| = 
\begin{bmatrix}
0 & g_1 & g_2 & \dots & g_n \\
g_1 & F_{11} & F_{12} & \dots & F_{1n} \\
g_2 & F_{21} & F_{22} & \dots & F_{2n} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
g_n & F_{n1} & F_{n2} & \dots & F_{nn}
\end{bmatrix}
$$

where $|\bar{\mathbf{H}}| = |\bar{H}_n|$ because the $n \times n$ principal minor is bordered.

In this case, if all the principal minors are negative, i.e. $|\bar{H}_2|, |\bar{H}_3|, \ldots , |\bar{H}_n| < 0$, the bordered Hessian is said to be positive definite and satisfies the second‑order condition for a minimum.

On the other hand, if the principal minors alternate consistently in sign from positive to negative, i.e. $|\bar{H}_2| > 0, |\bar{H}_3| < 0, |\bar{H}_4| > 0$ etc., the bordered Hessian is negative definite, and meets the sufficient conditions for a maximum.

## Input‑Output Analysis

If $a_{ij}$ is a technical coefficient representing the value of input $i$ required to produce one dollar's worth of product $j$, the total demand for good $i$ can be expressed as

$$
x_{i} = a_{i1}x_{1} + a_{i2}x_{2} + \dots + a_{in}x_{n} + b_{i}
$$

where $b_i$ is the final demand for product $i$. What is important to realize here is that the total demand for a product consists of that product being the final demand plus that product being an intermediate good required for the production of other products.

In matrix form we have

$$
\mathbf{X} = \mathbf{A}\mathbf{X} + \mathbf{B}
$$

where, for an $n$ sector economy,

$$
\mathbf{X} = 
\begin{bmatrix}
x_1 \\ x_2 \\ \vdots \\ x_n
\end{bmatrix},
\quad
\mathbf{A} = 
\begin{bmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & a_{n2} & \dots & a_{nn}
\end{bmatrix},
\quad
\mathbf{B} = 
\begin{bmatrix}
b_1 \\ b_2 \\ \vdots \\ b_n
\end{bmatrix}.
$$

$\mathbf{A}$ is called the matrix of technical coefficients.

To find the output (intermediate and final goods) needed to satisfy demand, all we have to do is to solve for $\mathbf{X}$:

$$
\mathbf{X} - \mathbf{A}\mathbf{X} = \mathbf{B} \quad \Rightarrow \quad (\mathbf{I} - \mathbf{A})\mathbf{X} = \mathbf{B} \quad \Rightarrow \quad \mathbf{X} = (\mathbf{I} - \mathbf{A})^{-1}\mathbf{B}.
$$

## Characteristic Roots and Vectors (Eigenvalues and Eigenvectors)

For a square matrix $\mathbf{A}$:

a) All characteristic roots $\lambda$ are positive $\Rightarrow$ $\mathbf{A}$ is positive definite.  
b) All $\lambda$'s are negative $\Rightarrow$ $\mathbf{A}$ is negative definite.  
c) All $\lambda$'s are nonnegative and at least one $\lambda = 0$ $\Rightarrow$ $\mathbf{A}$ is positive semi‑definite.  
d) All $\lambda$'s are nonpositive and at least one $\lambda = 0$ $\Rightarrow$ $\mathbf{A}$ is negative semi‑definite.  
e) Some $\lambda$'s are positive and some negative $\Rightarrow$ $\mathbf{A}$ is sign indefinite.

Let's take an example.

Given a square matrix

$$
\mathbf{A} = 
\begin{bmatrix}
-6 & 3 \\
3 & -6
\end{bmatrix}
$$

To find the characteristic roots (eigenvalues) of $\mathbf{A}$, we simply set $|\mathbf{A} - \lambda \mathbf{I}| = 0$:

$$
|\mathbf{A} - \lambda \mathbf{I}| = 
\begin{vmatrix}
-6 - \lambda & 3 \\
3 & -6 - \lambda
\end{vmatrix} = 0
$$

This means

$$
(-6 - \lambda)(-6 - \lambda) - 9 = 0 \\
\lambda^2 + 12\lambda + 27 = 0 \\
(\lambda + 9)(\lambda + 3) = 0 \\
\lambda = -9, -3.
$$

Since both characteristic roots $\lambda$ are negative, we say $\mathbf{A}$ is negative definite.

Note:

$$
\text{(i) } \sum \lambda_i = \operatorname{tr}(\mathbf{A}), \qquad
\text{(ii) } \prod \lambda_i = |\mathbf{A}|.
$$

Let's continue with the example above to find the characteristic vector.

We know one of the roots $\lambda = -9$, so substituting in the characteristic matrix gives

$$
(\mathbf{A} - \lambda \mathbf{I})\mathbf{v} = \mathbf{0} \quad \Rightarrow \quad
\begin{bmatrix}
-6 - (-9) & 3 \\
3 & -6 - (-9)
\end{bmatrix}
\begin{bmatrix}
v_1 \\ v_2
\end{bmatrix}
= 
\begin{bmatrix}
3 & 3 \\
3 & 3
\end{bmatrix}
\begin{bmatrix}
v_1 \\ v_2
\end{bmatrix}
= 
\begin{bmatrix}
0 \\ 0
\end{bmatrix}.
$$

Since the coefficient matrix is linearly dependent, there are infinite number of solutions. The product of the matrices gives two equations which are identical:

$$
3v_1 + 3v_2 = 0 \quad \Rightarrow \quad v_2 = -v_1.
$$

By normalizing we have

$$
v_1^{2} + v_2^{2} = 1.
$$

Substituting $v_2 = -v_1$ gives

$$
v_1^{2} + (-v_1)^{2} = 1 \quad \Rightarrow \quad 2v_1^{2} = 1 \quad \Rightarrow \quad v_1^{2} = \frac{1}{2}.
$$

Taking the positive square root gives $v_1 = \sqrt{1/2} = \frac{\sqrt{2}}{2}$ and substituting into $v_2 = -v_1$ gives $v_2 = -\frac{\sqrt{2}}{2}$. That is

$$
\mathbf{v}_1 = 
\begin{bmatrix}
\frac{\sqrt{2}}{2} \\[4pt]
-\frac{\sqrt{2}}{2}
\end{bmatrix}.
$$

Using the second characteristic root $\lambda = -3$:

$$
(\mathbf{A} - \lambda \mathbf{I})\mathbf{v} = 
\begin{bmatrix}
-6 - (-3) & 3 \\
3 & -6 - (-3)
\end{bmatrix}
\begin{bmatrix}
v_1 \\ v_2
\end{bmatrix}
= 
\begin{bmatrix}
-3 & 3 \\
3 & -3
\end{bmatrix}
\begin{bmatrix}
v_1 \\ v_2
\end{bmatrix}
= 
\begin{bmatrix}
0 \\ 0
\end{bmatrix}.
$$

Multiplying out gives $-3v_1 + 3v_2 = 0$ and $3v_1 - 3v_2 = 0$, so $v_1 = v_2$.

Normalizing as before:

$$
v_1^2 + v_2^2 = 1 \quad \Rightarrow \quad 2v_1^2 = 1 \quad \Rightarrow \quad v_1 = \frac{\sqrt{2}}{2}.
$$

Hence,

$$
\mathbf{v}_2 = 
\begin{bmatrix}
\frac{\sqrt{2}}{2} \\[4pt]
\frac{\sqrt{2}}{2}
\end{bmatrix}.
$$