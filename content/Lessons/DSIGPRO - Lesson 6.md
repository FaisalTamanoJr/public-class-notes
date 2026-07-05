---
title: Rational Z-Transform and Transfer Function
draft: false
tags:
  - DSIGPRO
date: 2026-06-18, 21:45
---

## Sources

1.  Rational Z-Transform and Transfer Function (Lecture Slides & Annotations)
2. Lecture Notes

## Example 1 - Poles and Zeros Part 1


> [!INFO] Problem 1
> Determine the pole-zero plot for the signal
> $$
> x[n] = a^nu[n]
> $$

$$
\begin{align*}
X(z) &= \frac{1}{1-az^{-1}} \cdot \frac{z}{z}
\end{align*}
$$

$$
\boxed{
\begin{align*}
X(z) &= \frac{z}{z-a} \\
\text{zero: } z_{1}&=0 \\
\text{pole: } z-a&=0 \\
z&=a \text{, } P_{1}=a
\end{align*}
}
$$

## Example 2 - Poles and Zeros Part 2

> [!INFO] Problem 2
> Determine the pole-zero plot for the signal
> $$
> x[n] = \begin{cases}
> a^n & 0\leq n\leq M-1 \\
> 0 & \text{elsewhere}
> \end{cases}
> $$

$$
\begin{align*}
X(z) &= \sum^{M-1}_{n=0}a^nz^{-n} \\
&= \sum^N_{{n=1}} (az^{-1})^n \\
&= \frac{1-(az^{-1})^M}{1-az^{-1}} \\
&= \frac{1-(az^{-1})^M}{1-az^{-1}} \cdot \frac{z^{M}}{z^M} \\
&= \frac{z^M - a^M}{z^M - az^{M-1}} = \frac{(z-a)(z-z_{1})(z-z_{2})\dots(z-z_{M-1})}{(z-a)z^{M-1}} \\
X(z)&= \frac{(z-z_{1})(z-z_{2})\dots (z-z_{M-1})}{z^{M-1}} \\
\end{align*}
$$

Without pole-zero cancellation

$$
\begin{align*}
z^M &= a^M &\text{has M roots} \\
z_{k} &= ae^{j\frac{2\pi k}{M},} &k=0,1,2\dots, M-1
\end{align*}
$$

$$
\begin{align*}
\text{if }M&=8  \\
z_{k} &= ae^{j\frac{2\pi k}{M},} \\
&= ae^{j\frac{2\pi k}{8},} \\
z_{k} &= ae^{j \frac{\pi}{4}k}
\end{align*}
$$

Therefore, each poles and zeros are $45^\circ$ or $\frac{\pi}{4}$ away from other poles and zeros

> [!TIP]- Tip 2. Summation of $A^n$
> $$
> \sum^N_{n=1}A^n=\frac{1-A^{N+1}}{1-A}\text{, }|A|<1
> $$


## Example 4 - Transfer Function


> [!NOTE] Problem 4
> Determine the system function & unit sample response based on the difference equation:
> 
> $$
> y[n] = \frac{1}{2}y[n-1]+2x[n]
> $$


Taking the z-transform of both sides

$$
\begin{align*}
Y(z) &= \frac{1}{2}z^{-1}Y(z)+2X(z) \\
\left( 1-\frac{1}{2}z^{-1} \right)Y(z) &= 2X(z) \\
H(z) &= \frac{Y(z)}{X(z)} \\
&= \frac{2}{1-\frac{1}{2}z^{-1}}
\end{align*}
$$

Transfer function:

$$
\boxed{
H(z) = \frac{2}{1-\frac{1}{2}z^{-1}}
}
$$

Take the inverse z-transform of H(z)

$$
\boxed{
h[n] = 2\left( \frac{1}{2} \right)^n u[n]
}
$$

## Example 5 - Causal LTI System


> [!INFO] Problem 5
> If input:
> 
> $$
> x[n] = \left( \frac{1}{2} \right)^n u[n] - \frac{1}{4} \left( \frac{1}{2} \right)^{n-1} u[n-1]
> $$
> 
> then output:
> 
> $$
> y[n]=\left(\frac{1}{3}\right)^n u[n]
> $$
> 
> a.) Does $H(z)$ satisfy the foregoing conditions?
> 
> b.) What is the difference equation that describe this system?
> 
> c.) Is the system stable?

### a.) Transfer Function

$$
H(z) = \frac{Y(z)}{X(z)}
$$

$$
\begin{align*}
\text{From } y[n] &= \left( \frac{1}{3} \right)^nu[n], \\
Y(z) &= \frac{1}{1-\frac{1}{3}z^{-1}}
\end{align*}
$$

$$
\begin{align*}
\text{From } x[n] &= \left( \frac{1}{2} \right)^n u[n] - \frac{1}{4}\left( \frac{1}{2} \right)^{n-1} u[n-1] \\
X(z) &= Z\left\{\left( \frac{1}{2} \right)^n u[n] \right\}-\frac{1}{4}z^{-1}Z\left\{\left( \frac{1}{2} \right)^nu[n]\right\} \\
&=\left( 1-\frac{1}{4}z^{-1} \right)Z\left\{\left( \frac{1}{2} \right)^nu[n]\right\} \\
X(z) &= \frac{1-\frac{1}{4}z^{-1}}{1-\frac{1}{2}z^{-1}}
\end{align*}
$$

$$
H(z) = \frac{\displaystyle \frac{1}{1-\frac{1}{3}z^{-1}}}{\displaystyle \frac{1-\frac{1}{4}z^{-1}}{1-\frac{1}{2}z^{-1}}} 
$$

$$
\boxed{
H(z) = \frac{1-\frac{1}{2}z^{-1}}{\left( 1-\frac{1}{3}z^{-1} \right)\left( 1-\frac{1}{4}z^{-1} \right)}\text{, } ROC: |z| > \frac{1}{3}
}
$$

### b.) Difference Equation

$$
H(z) = \frac{Y(z)}{X(z)} = \frac{1-\frac{1}{2}z^{-1}}{1-\frac{7}{12}z^{-1}+\frac{1}{12}z^{-2}}
$$

$$
\left( 1-\frac{7}{12}z^{-1}+\frac{1}{12}z^{-2} \right)Y(z) = \left( 1-\frac{1}{2}z^{-1} \right)X(z)
$$

$$
z^{-1} \left\{ Y(z) - \frac{7}{12}z^{-1}Y(z)+\frac{1}{12}z^{-2}Y(z) = X(z) - \frac{1}{2}z^{-1}X(z) \right\}z^{-1}
$$

$$
y[n]-\frac{7}{12}y[n-1]+\frac{1}{12}y[n-2] = x[n]-\frac{1}{2}x[n-1]
$$

$$
\boxed{
y[n]=\frac{7}{12}y[n-1]-\frac{1}{12}y[n-2]+x[n]-\frac{1}{2}x[n-1]
}
$$

### c.) Is the system causal and stable

ROC: $|z| > \frac{1}{3}$

The system is **causal** and **stable**