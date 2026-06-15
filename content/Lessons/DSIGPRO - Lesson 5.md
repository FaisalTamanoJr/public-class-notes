---
title: Direct Z Transform
draft: false
tags:
  - DSIGPRO
date: 2026-06-15, 21:45
---

## Sources

1.  DirectZTransform (Lecture Slides)
2. Lecture Notes

## Example 1

> [!INFO] Problem 1.a.
> $$
> x_{1}[n] = \{\underset{\uparrow}1,2,5,7,0,1\}
> $$

$$
\begin{align}

x_{1}[n] &= \delta[n] + 2 \delta[n-1] + 5 \delta[n-2] + 7\delta[n-3] + \delta[n-5]  \\ \\

X_{1}(z) &= \sum^5_{n=0}x(n)z^{-n} \\
&= x[0]z^{-0} + x[1]z^{-1} + x[2]z^{-2} + x[3]z^{-3} + x[4]z^{-4} + x[5]z^{-5}  \\
\end{align}
$$


$$
\boxed{X_{1}(z)=1 + 2z^{-1} + 5z^{-2}+ 7z^{-3} + z^{-5}}
$$

Region of Convergence (ROC): entire z-plane

> [!INFO] Problem 1.b.
> $$
> x_{2}[n] = \{1,2,\underset{\uparrow}5,7,0,1\}
> $$

$$
\boxed{X_{2}(z) = z^2 + 2z + 5 + 7z^{-1} + z^{-3}}
$$

> [!INFO] Problem 1.c.
> 
> $$
> x_{3}[n] = \{\underset{\uparrow}0,0,1,2,5,7,0,1\}
> $$

$$
\boxed{X_{3}(z) = z^{-2} + 2z^{-3} + 5z^{-4} + 7z^{-5} + z^{-7}}
$$

ROC: entire z-plane, except $z=0$

> [!INFO] Problem 1.d.
> 
> $$
> \begin{align}
> x_{4}[n]=\delta[n]
> \end{align}
> $$

$$
\begin{align}
X_{4}(z) &= \sum^{\infty }_{n=-\infty}\delta [n] z^{-n} \\
&= \delta[0]z^{-0} \\
&=1(1) \\
\end{align}
$$
$$
\boxed{X_{4}(z)=1}
$$

ROC: entire z-plane

> [!INFO] Problem 1.e.
> 
> $$
> \begin{align}
> x_{5}[n]=\delta[n-k], && k>0
> \end{align}
> $$

$$
\begin{align}
X_{5}(z) &=\sum^{\infty}_{-\infty}\delta(n-k)z^{-n} \\
&=s[0]z^{-k}
\end{align}
$$

$$
\boxed{X_{5}{(z)} = z^{-k},\text{ }k>0}
$$

> [!INFO] Problem 1.f.
> 
> $$
> \begin{align}
> x_{6}[n]=\delta[n+k], && k>0
> \end{align}
> $$

$$
\boxed{X_{6}{(z)} = z^{k},\text{ }k>0}
$$
## Example 2


> [!INFO] Problem 2.a.
> 
> $$
> \begin{align}
> x[n]=\alpha^n u[n]=\begin{cases}
> a^n & n\geq0 \\
> 0 & n<0
> \end{cases}
> \end{align}
> $$

$$
\begin{align}
X(z) &= \sum^{\infty}_{n=0}\alpha^nz^{-n} \\
&=\sum^{\infty}_{n=0}(\alpha z^{-1})^{n} \\
&=\frac{1}{1-\alpha z^{-1}} & |\alpha z^{-1} | < 1 \\
&=\frac{1}{1-\alpha z^{-1}} & |z| > |\alpha|
\end{align}
$$


> [!TIP]- Tip 2.a.1. Summation of Exponentials $(0\leq n <\infty)$
> $$
> \begin{align}
> \sum^{\infty}_{n=0}A^n &= 1+A+A^2+A^3+\dots \\
> &= \frac{1}{1-A} & |A| < 1
> \end{align}
> $$

> [!TIP]- Tip 2.a.2. $|z|>|\alpha|$
> $$
> \begin{align}
> |\alpha z^{-1}| &< 1 & \text{negative exponent means inverse/reciprocate}\\
> |\alpha \left( \frac{1}{z} \right)| &< 1 & \text{multiply both sides by }z \\
> |\alpha| &< |z| \\
> |z| &> |a|
> \end{align}
> $$

Transform pairs:

$$
\boxed{a^{n}u[n]\xleftrightarrow{\text{z}} \frac{1}{1-az^{-1}}\text{, }|z|>|\alpha|}
$$

let $\alpha=1$:

$$
\boxed{u[n]\xleftrightarrow{\text{z}} \frac{1}{1-z^{-1}}\text{, }|z|>1}
$$

> [!INFO] Problem 2.b.
> 
> $$
> \begin{align}
> x[n]=-\alpha^n u[-n-1]=\begin{cases}
> 0 & n\geq0 \\
> -\alpha^n & n\leq-1
> \end{cases}
> \end{align}
> $$


> [!TIP]- Tip 2.b.1. What to do with $u[-n-1]$?
> $$
> \begin{align}
> u[n] &\to 0 \leq n <\infty & \text{fold and shift}\\
> u[-n-1] &\to -\infty< n \leq -1
> \end{align}
> $$

$$
\begin{align}
X(z) &= \sum^{-1}_{n=-\infty }-\alpha^nz^{-n} \\
&= -\sum^{-1}_{n=-\infty }\alpha^nz^{-n} \\
&= -\sum^{\infty}_{n=1 }\alpha^{-n}z^{n} \\
&=-\frac{\alpha^{-1}z}{1-\alpha^{-1}z} & |a^{-1}z| < 1 \\
&=-\frac{1}{\alpha^{-1}z-1} & |z| < |\alpha| \\
&=\frac{1}{1-\alpha^{-1}z} & |z| < |\alpha|
\end{align}
$$

> [!TIP]- Tip 2.b.2. Summation of Exponentials $(1 \leq n < \infty)$
> $$
> \begin{align}
> \sum^{\infty}_{n=1}A^n &= A+A^2+A^3+\dots \\ \\
> &= A(1+A+A^2+\dots) \\
> &= A(\frac{1}{1-A}) & |A| < 1
> \end{align}
> $$

Transform pairs

$$
\boxed{-a^{n}u[-n-1]\xleftrightarrow{\text{z}} \frac{1}{1-az^{-1}}\text{, }|z|<|\alpha|}
$$

> [!INFO] Problem 2.c.
>
> $$
> x[n] = \alpha^n u[n] + b^{n}u[-n-1]
> $$

