---
draft: false
tags: [NUMMETS]
title: Interpolation
date: 2024-07-19, 09:57
---

> [!INFO]- Keywords
> [[interpolation]], [[Newton's polynomials]], [[Lagrange's polynomials]], [[linear interpolation]], [[quadratic interpolation]]

The general formula for an $n$th-order polynomial is

$$
f(x)=a_{0}+a_{1}x+a_{2}x^2+\dots+a_{n}x^n
$$

Moreover, for $n+1$ data points, there is only one polynomial of order $n$ that passes through all the points—which we can determine using *polynomial interpolation*. Obtaining that polynomial will allow us to compute for intermediate values between data points.

There are two popular mathematical formats to express this polynomial: the *Newton* and the *Lagrange polynomials*.

## Newton’s Divided-Difference Interpolating Polynomials

### Linear Interpolation

*Linear interpolation*, the simplest form of interpolation, involves connecting two data points using a straight line.

Characteristics

- First order interpolating polynomial.
- The accuracy of its approximation increases as the interval between the data points decreases.

Formula

$$
f_{1}(x)=f(x_{0})+\frac{f(x_{1})-f(x_{0})}{x_{1}-x_{0}}(x-x_{0})
$$

The term $\displaystyle\frac{f(x_{1})-f(x_{0})}{x_{1}-x_{0}}$ represents the slope of the line connecting the points and is also the finite-divided-difference approximation of the first derivative.

### Quadratic Interpolation

We can obtain a second-order interpolating polynomial (or a quadratic polynomial) when we have three data points given. A convenient for this purpose is

$$
f_{2}(x)=b_{0}+b_{1}(x-x_{0})+b_{2}(x-x_{0})(x-x_{1})
$$

where

$$
\begin{align}
b_{0} &= f(x_{0}) \\ \\
b_{1} &= \frac{f(x_{1})-f(x_{0})}{x_{1}-x_{0}} \\ \\
b_{2} &= \frac{\displaystyle\frac{f(x_{2})-f(x_{1})}{x_{2}-x_{1}}-\frac{f(x_{1})-f(x_{0})}{x_{1}-x_{0}}}{x_{2}-x_{0}}
\end{align}
$$

The term $b_{1}$ represents the slope of the line connecting the points $x_{0}$ and $x_{1}$, and, as such, is equivalent to the linear interpolation from $x_{0}$ to $x_{1}$. On the other hand, the $b_{2}(x-x_{0})(x-x_{1})$ introduces the second-order curvature.

### General Form

The general form for an $n$th-order polynomial (or *Newton’s divided-difference interpolating polynomial*) is

$$
f_{n}(x)=b_{0}+b_{1}(x-x_{0})+\dots+b_{n}(x-x_{0})(x-x_{1})\dots(x-x_{n-1})
$$

For an $n$th-order polynomial, $n+1$ data points are required in order to evaluate the following coefficients:

$$
\begin{align}
b_{0}&=f(x_{0}) \\
b_{1}&=f[x_{1},x_{0}] \\
b_{2}&=f[x_{2},x_{1},x_{0}] \\
\vdotswithin{=} \\
b_{n}&=f[x_{n},x_{n-1},\dots,x_{1},x_{0}]
\end{align}
$$

To find the $n$th finite divided difference

$$
f[x_{n},x_{n-1},\dots,x_{1},x_{0}]=\frac{f[x_{n},x_{n-1},\dots,x_{1}]-f[x_{n-1},x_{n-2},\dots,x_{0}]}{x_{n}-x_{0}}
$$

> [!TIP]- Graphical Depiction of the Nature of Finite Divided Difference
>
> | $i$ | $x_{i}$ | $f(x_{i})$ | First            | Second                 | Third                        |
> | --- | ------- | ---------- | ---------------- | ---------------------- | ---------------------------- |
> | $0$ | $x_{0}$ | $f(x_{0})$ | $f[x_{1},x_{0}]$ | $f[x_{2},x_{1},x_{0}]$ | $f[x_{3},x_{2},x_{1},x_{0}]$ |
> | $1$ | $x_{1}$ | $f(x_{1})$ | $f[x_{2},x_{1}]$ | $f[x_{3},x_{2},x_{1}]$ |                              |
> | $2$ | $x_{2}$ | $f(x_{2})$ | $f[x_{3},x_{2}]$ |                        |                              |
> | $3$ | $x_{3}$ | $f(x_{3})$ |                  |                        |                              |

### Errors

The $n$th-order interpolating polynomial will have a truncation error expressed as

$$
R_{n}=f[x,x_{n},x_{n-1},\ldots,x_{0}](x-x_{0})(x-x_{1})\cdots(x-x_{n})
$$

where $f[x,x_{n},x_{n-1},\ldots,x_{0}]$ is the $(n+1)$th finite divided difference. Nevertheless, because it has $f(x)$, it cannot be solved for the error—unless the additional data point $f(x_{n+1})$ is available. If the additional data point is available, we can estimate the error using the following formula:

$$
R_{n}=f[x_{n+1},x_{n},x_{n-},\ldots,x_{0}](x-x_{0})(x-x_{1})\cdots(x-x_{n})
$$

The issue with higher-order interpolating polynomials, however, is that they are highly sensitive to data errors. When interpolation is applied, they often yield inaccurate predictions. For this reason, they are better suited for exploratory data analysis.

## Lagrange Interpolating Polynomials

The *Lagrange interpolating polynomial* is a reformulation of the Newton’s polynomial that avoids divided differences, thus

$$
f_{n}(x)=\sum^n_{i=0}L_{i}(x)f(x_{i})
$$

where

$$
L_{i}(x)\,=\,\prod_{\substack{\displaystyle j=0\\ \displaystyle j\neq1}}^{\displaystyle n}{\frac{\,x\,-\,x_{\displaystyle j}\,}{x_{\displaystyle i}\,-\,x_{\displaystyle j}\,}}
$$

where $\prod$ refers to the *product*.

$L_{i}(x)$ will be $1$ at $x=x_{i}$ and $0$ at any other points; as a result, $L_{i}(x)f(x_{i})$ takes on the value of $f(x_{i})$ at $x_{i}$.

The error estimate can be computed with

$$
R_{n}= f[x,x_{n},x_{n-1},\dots,x_{0}] \prod^n_{i=0}(x-x_{i})
$$

## Newton or Lagrange?

For exploratory computations, Newton’s method is preferred because it gives insight to the different-order formulas’ behavior; it is suited for cases where the polynomial’s order is unknown. Furthermore, because Newton’s method employs a finite difference, we can easily integrate the error estimate to it.

Lagrange is preferred over Newton in cases where only one interpolation is to be performed because it is easier to program—it does not depend on divided differences, but the polynomial’s order must be known beforehand.

## Sources

1. Numerical Methods for Engineers by Steven Chapra and Raymond Canale (Chapter 18)
