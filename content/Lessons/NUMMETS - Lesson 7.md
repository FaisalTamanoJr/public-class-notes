---
draft: false
tags: [NUMMETS]
title: Numerical Integration
date: 2024-07-19, 19:54
---

> [!INFO]- Keywords
> [[Newton-Cotes formulas]], [[trapezoidal rule]], [[Simpsons rule]], [[strip method]], [[closed forms of Newton-Cotes formulas]], [[open forms of Newton-Cotes formulas]]

## Introduction

*Newton-Cotes formulas* are numerical integration schemes that simplify a complicated function/data into a approximating function:

$$
I=\int_{a}^{b}f(x)\,d x\cong\int_{a}^{b}f_{n}(x)\,d x
$$

where $f_{n}(x)=$ a polynomial with the form

$$
f_{n}(x)\,=\,a_{0}\,+\,a_{1}x\,+\,\cdot\cdot\cdot\,+\,a_{n-1}x^{n-1}\,+\,a_{n}x^{n}
$$

where $n$ is the polynomial’s order.

We can use a piecewise function and straight lines to approximate the integral of a polynomial using a method known as the *strip method*. Besides this, we can two possible forms of Newton-Cotes formulas: closed and open. The *closed forms* knows the data points at the beginning and end of the limits of integration, whereas *open forms* have integration limits that extend beyond the data’s range.

## Trapezoidal Rule

The *trapezoidal rule* is applicable in cases where the polynomial is in the first order. When given a first order polynomial like

$$
I=\int^b_{a} f_{1}(x)dx
$$

we can use the trapezoidal rule and approximate the resulting integration

$$
I=(b-a) \frac{f(a)+f(b)}{2}
$$

It is based on the geometrical approximation of the area of a trapezoid, which is formed by connecting the two points—$f(a)$ and $f(b)$—with a straight line. Hence, it can also be represented as

$$
I \cong \underbrace{(b-a)}_{\text{Width}} \times \underbrace{\frac{f(a)+f(b)}{2}}_{\text{Average height}}
$$

All Newton-Cotes closed formulas follow this format but only differ with how the average height is formulated.

### Error

To estimate the local truncation error of a single application of the trapezoidal rule, we use

$$
E_{t} = -\frac{1}{12}\bar{f}''(\xi)(b-a)^3
$$

where $\xi$ lies somewhere in the interval from $a$ to $b$. The trapezoidal rule will be exact when the function being integrated is linear—error occurs when we have higher-order derivatives.

### Multiple Application

![TODO](https://bartonfamilylaw.com.au/wp-content/uploads/2018/05/to-do.jpg)

#### Error

![TODO](https://bartonfamilylaw.com.au/wp-content/uploads/2018/05/to-do.jpg)

## Simpson’s Rule

*Simpson’s rules* use higher-order polynomials to estimate an integral.

### Simpson’s 1/3 Rule

The Simpson’s rule is

$$
I \cong \frac{h}{3}[f(x_{0})+4(x_{1})+f(x_{2})]
$$

where $h = \frac{\displaystyle b-a}{\displaystyle 2}$

The $\frac{h}{3}$ is what gives it the 1/3 in its name. It can also be expressed in the format

$$
I \cong \underbrace{(b-a)_{}}_{\text{Width}} \underbrace{\frac{f(x_{0})+4f(x_{1})+f(x_{2})}{6}}_{\text{Average height}}
$$

The Simpson’s 1/3 rule has a error estimate of

$$
E_{t}=-\frac{1}{90}h^5\bar{f}^{(4)}(\xi)
$$

or

$$
E_{t}=-\frac{(b-a)^5}{2880}\bar{f}^{(4)}(\xi)
$$

where $\xi$ lies somewhere in the interval from $a$ to $b$.

This rule is more accurate than the trapezoidal rule and its error is proportional to the fourth derivative. Although it is based on only three points, it is third-order accurate; thus, it yields exact results for cubic polynomials even though it is derived from a parabola.

#### Multiple-Application

![TODO](https://bartonfamilylaw.com.au/wp-content/uploads/2018/05/to-do.jpg)

### Simpson’s 3/8 Rule

This rule can be fit to four points and integrated to get

$$
I\cong\frac{3h}{8}[f(x_{0})\,+3f(x_{1})\,+3f(x_{2})\,+\,f(x_{3})\,]
$$

where $h=\frac{\displaystyle b-a}{\displaystyle 3}$.

The $\frac{3h}{8}$ is what gives it the 3/8 in its name. It can also be expressed in the format

$$
I \cong \underbrace{(b-a)_{}}_{\text{Width}} \underbrace{\frac{f(x_{0})+3f(x_{1})+3f(x_{2})+f(x_{3})}{8}}_{\text{Average height}}
$$

It has an error estimate of

$$
E_{t}=- \frac{(b-a)^5}{6480}f^{(4)}(\xi)
$$

In addition, it is more accurate than the 1/3 rule.

This rule is preferred over the 1/3 one whenever the number of segments is odd.

## Sources

1. Numerical Methods for Engineers by Steven Chapra and Raymond Canale (Chapter 21)
