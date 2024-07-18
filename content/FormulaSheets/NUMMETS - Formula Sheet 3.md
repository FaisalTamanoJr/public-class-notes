---
draft: false
tags: [NUMMETS]
title: Systems of Linear Equations
---

## Systems of Linear Equations

### Naive Gauss Elimination

> [!EXAMPLE] Summarized steps
> 1. Keep eliminating the unknowns until there is one equation with only one unknown; thus, the value of that single unknown is obtained.
> 2. Using the previously solved unknown, use back-substitution to solve for the values of the other unknowns

#### Forward Elimination of Unknowns

Suppose we are a given an equation:

$$
\begin{align}a_{11}x_{1}\,+\,a_{12}x_{2}\,+\,a_{13}x_{3}\,+\,\cdots\,+\,a_{1n}x_{n}&=\,b_{1}\\a_{21}x_{1}+\,a_{22}x_{2}\,+\,a_{23}x_{3}\,+\,\cdots\,+\,a_{2n}x_{n}&=\,b_{2}\\&\vdotswithin{=} \notag \\a_{n1}x_{1}\,+\,a_{n2}x_{2}\,+\,a_{n3}x_{3}\,+\,\cdots\,+\,a_{n n}x_{n}&=\,b_{n}\end{align}
$$

If we want to get $a'_{n1},a'_{n2},\dots a'_{nn}$—the coefficients of equation $n$ after the first variable has been eliminated—we could solve each one of these coefficients using a formula like:

$$
a'_{nm}=a_{nm}-\left(\frac{a_{n1}}{a_{11}}\right)(a_{1m})
$$

In order to get $a^{i}$ equations, we should already have the $a^{i-1}$ equation to use it as a basis for eliminating $i^{th}$ variable (just like how we use $a'$ as a basis for $a$).[^i]

Eliminating other variables just follow a similar pattern, and, as such:

$$
a^{i}_{nm}=a^{i-1}_{nm}-\left(\frac{a^{i-1}_{ni}}{a^{i-1}_{ii}}\right)(a_{im})
$$

We use this technique and incrementally eliminate downwards until we are left with an equation with only a single variable. Afterwards, we solve for the single variable’s value, then use it to perform backward substitution to get the values of other variables.

### Gauss-Jordan Method

This is a variation of Gauss elimination where the elimination step results in an identity matrix instead of a triangular one. For this reason, we aim to make the matrix look like

$$
\left[\begin{matrix} 1&0&0 \\ 0&1&0 \\ 0&0&1 \end{matrix}\right]
$$

To do this, we perform something similar to the following steps:

(These steps can only be applied for a 3 by 3 matrix)

1. $R'_{1}=\frac{1}{a_{11}}r_{1}$
2. $R'_{2}=r_{2}-a_{21}r_{1}'$ and $R'_{3}=r_{3}-a_{31}r'_{1}$
3. $R''_{2}=\frac{1}{a'_{22}}r'_{2}$
4. $R''_{1}=r'_{1}-a'_{{12}}r''_{2}$ and $R''_{3}=r'_{3}-a'_{{32}}r''_{2}$
5. $R'''_{3}=\frac{1}{a''_{33}}r''_{3}$
6. $R'''_{1}=r''_{1}-a''_{{13}}r'''_{3}$ and $R'''_{2}=r''_{2}-a''_{{23}}r'''_{3}$

Using the vectors (the last column), we can obtain the values of the variables (with the top being $x_{1}$ and the bottom being $x_{n}$).

### LU Decomposition

$\begin{align} [A]\{X\}&=\{B\} \\ [U][L]&=[A] \\ [L]\{D\}&=\{B\} \\ [U]\{X\}&=\{D\} \end{align}$

- Where $[A]$ is the original matrix of coefficients;
- $\{X\}$ is the $x$ variables;
- $\{B\}$ is the vectors;
- $\{D\}$ is equivalent to:
	- $\left\{\begin{matrix} d_{1} \\ d_{2} \\ d_{3} \end{matrix}\right\}$
- $[U]$ is equivalent to:
	- $\left[\begin{matrix} a_{11}&a_{12}&a_{13} \\ 0&a'_{22}&a'_{23} \\ 0&0&a''_{33} \end{matrix}\right]$
- $[L]$ is equivalent to:
	- $\left[\begin{matrix} 1&0&0 \\ f_{21}&1&0 \\ f_{31}&f_{32}&1 \end{matrix}\right]$
		- $f_{21}=\frac{a_{21}}{a_{11}}$
		- $f_{31}=\frac{a_{31}}{a_{11}}$
		- $f_{32}=\frac{a'_{32}}{a'_{22}}$

> [!EXAMPLE] Steps
> 1. Perform LU decomposition (get the values of $[L]$ and $[U]$)
> 2. Use forward substitution to get $\{D\}$
> 3. Use backward substitution to get $\{X\}$

### The Matrix Inverse

$[A][A]^{-1}=I$

To obtain the first column of the inverse matrix:

${b}=\left\{ \begin{align} 1\\0\\0 \end{align} \right\}$

To obtain the second column of the inverse matrix:

${b}=\left\{ \begin{align} 0\\1\\0 \end{align} \right\}$

To obtain the third column of the inverse matrix:

${b}=\left\{ \begin{align} 0\\0\\1 \end{align} \right\}$

Employ LU decomposition to find the inverse matrix: solve for $x$ using the LU decomposition equations and keep changing the $b$ for each computation to find the values of each column.

1. Solve for $[U]$ and $[L]$
2. $[L]\{D\}=\{B\}$ (use forward substitution)
3. $[U]\{X\}=\{D\}$ (use backward substitution)

### Gauss-Seidel Method

$$
\begin{align} x_{1}&=\frac{b_{1}-a_{12}x_{2}-a_{13}x_{3}}{a_{11}} \\ x_{2}&=\frac{b_{2}-a_{21}x_{1}-a_{23}x_{3}}{a_{22}}  \\ x_{3}&=\frac{b_{3}-a_{31}x_{1}-a_{32}x_{2}}{a_{33}} \end{align}
$$

> [!tip]
> - You can start the solution process with the initial guesses being $0$
> - Use previous/latest values to substitute for the variables

To obtain the percent relative error:

$$
|\epsilon_{a,i}|=\left| \frac{x_{i}^j-x_{i}^{j-1}}{x_{i}^j} \right|\times{100}\%
$$

[^i]: $i$ is referring to the order and not the exponent
