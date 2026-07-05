---
title: Direct Z Transform
draft: false
tags:
  - DSIGPRO
date: 2026-06-15, 21:45
---

## Sources

1.  DirectZTransform (Lecture Slides & Annotations)
2. Lecture Notes

## Example 1 - Region of Convergence Part 1

> [!INFO] Problem 1.a.
> $$
> x_{1}[n] = \{\underset{\uparrow}1,2,5,7,0,1\}
> $$

$$
\begin{align*}

x_{1}[n] &= \delta[n] + 2 \delta[n-1] + 5 \delta[n-2] + 7\delta[n-3] + \delta[n-5]  \\ \\

X_{1}(z) &= \sum^5_{n=0}x(n)z^{-n} \\
&= x[0]z^{-0} + x[1]z^{-1} + x[2]z^{-2} + x[3]z^{-3} + x[4]z^{-4} + x[5]z^{-5}  \\
\end{align*}
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
> \begin{align*}
> x_{4}[n]=\delta[n]
> \end{align*}
> $$

$$
\begin{align*}
X_{4}(z) &= \sum^{\infty }_{n=-\infty}\delta [n] z^{-n} \\
&= \delta[0]z^{-0} \\
&=1(1) \\
\end{align*}
$$
$$
\boxed{X_{4}(z)=1}
$$

ROC: entire z-plane

> [!INFO] Problem 1.e.
> 
> $$
> \begin{align*}
> x_{5}[n]=\delta[n-k], && k>0
> \end{align*}
> $$

$$
\begin{align*}
X_{5}(z) &=\sum^{\infty}_{-\infty}\delta[n-k]z^{-n} \\
&=\delta[0]z^{-k}
\end{align*}
$$

$$
\boxed{X_{5}{(z)} = z^{-k},\text{ }k>0}
$$

> [!INFO] Problem 1.f.
> 
> $$
> \begin{align*}
> x_{6}[n]=\delta[n+k], && k>0
> \end{align*}
> $$

$$
\boxed{X_{6}{(z)} = z^{k},\text{ }k>0}
$$
## Example 2 - Region of Convergence Part 2


> [!INFO] Problem 2.a.
> 
> $$
> \begin{align*}
> x[n]=\alpha^n u[n]=\begin{cases}
> a^n & n\geq0 \\
> 0 & n<0
> \end{cases}
> \end{align*}
> $$

$$
\begin{align*}
X(z) &= \sum^{\infty}_{n=0}\alpha^nz^{-n} \\
&=\sum^{\infty}_{n=0}(\alpha z^{-1})^{n} \\
&=\frac{1}{1-\alpha z^{-1}} & |\alpha z^{-1} | < 1 \\
&=\frac{1}{1-\alpha z^{-1}} & |z| > |\alpha|
\end{align*}
$$


> [!TIP]- Tip 2.a.1. Summation of Exponentials $(0\leq n <\infty)$
> $$
> \begin{align*}
> \sum^{\infty}_{n=0}A^n &= 1+A+A^2+A^3+\dots \\
> &= \frac{1}{1-A} & |A| < 1
> \end{align*}
> $$

> [!TIP]- Tip 2.a.2. $|z|>|\alpha|$
> $$
> \begin{align*}
> |\alpha z^{-1}| &< 1 & \text{negative exponent means inverse/reciprocate}\\
> |\alpha \left( \frac{1}{z} \right)| &< 1 & \text{multiply both sides by }z \\
> |\alpha| &< |z| \\
> |z| &> |a|
> \end{align*}
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
> \begin{align*}
> x[n]=-\alpha^n u[-n-1]=\begin{cases}
> 0 & n\geq0 \\
> -\alpha^n & n\leq-1
> \end{cases}
> \end{align*}
> $$


> [!TIP]- Tip 2.b.1. What to do with $u[-n-1]$?
> $$
> \begin{align*}
> u[n] &\to 0 \leq n <\infty & \text{fold and shift}\\
> u[-n-1] &\to -\infty< n \leq -1
> \end{align*}
> $$

$$
\begin{align*}
X(z) &= \sum^{-1}_{n=-\infty }-\alpha^nz^{-n} \\
&= -\sum^{-1}_{n=-\infty }\alpha^nz^{-n} \\
&= -\sum^{\infty}_{n=1 }\alpha^{-n}z^{n} \\
&=-\frac{\alpha^{-1}z}{1-\alpha^{-1}z} & |a^{-1}z| < 1 \\
&=-\frac{1}{\alpha z^{-1}-1} & |z| < |\alpha| \\
&=\frac{1}{1-\alpha z^{-1}} & |z| < |\alpha|
\end{align*}
$$

> [!TIP]- Tip 2.b.2. Summation of Exponentials $(1 \leq n < \infty)$
> $$
> \begin{align*}
> \sum^{\infty}_{n=1}A^n &= A+A^2+A^3+\dots \\ \\
> &= A(1+A+A^2+\dots) \\
> &= A(\frac{1}{1-A}) & |A| < 1
> \end{align*}
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


$$
\boxed{
\begin{align*}
X(z) = \underbrace{\frac{1}{1-\alpha z^{-1}}}_{\displaystyle|z|>|\alpha|} &- \underbrace{\frac{1}{1-bz^{-1}}}_{\displaystyle|z|<|b|}
\end{align*}
}
$$

Case $|\alpha| > |b|$:

ROC: 

There is no overlapping region, hence, the z-transform does not exist

Case $|\alpha|<|b|$:

ROC :

$$
\begin{align*} 
X(z) = \frac{1}{1-\alpha z^{-1}} &- \frac{1}{1-bz^{-1}} & |\alpha| < |z| < |b|
\end{align*}
$$

## Example 3 - Linearity Part 1


> [!INFO] Problem
> $$
> x[n] = \{3(2)^n-4(3)^n\}u[n]
> $$

$$
x[n] = a_{1}x_{1}[n]+a_{2}x_{2}[n]
$$

1st term:

$$
\begin{align*}
a_{1} &= 3 \\
x_{1}[n] &= 2^n \\
X_{1}(z) &= \frac{1}{1-2z^{-1}} & |z|>2
\end{align*}
$$

2nd term:

$$
\begin{align*}
a_{2} &= -4 \\
x_{2}[n] &= 3^n \\
X_{2}(z) &= \frac{1}{1-3z^{-1}} & |z|>3
\end{align*}
$$

Combined:

$$
\begin{align*}
X(z) &= a_{1}x_{1}(z)+a_{2}x_{2}(z) \\
&= \frac{3}{1-2z^{-1}} - \frac{4}{1-3z^{-1}}
\end{align*}
$$

ROC: $|z|>3$


> [!TIP]- Tip 3. ROC
> Causal:
> 
> ROC: $|z|>max\{P_{1},P_{2},\dots,P_{n}\}$
> 
> Non-Causal:
> 
> ROC: $|z|<min\{P_{1},P_{2},\dots,P_{n}\}$
> 

## Example 4 - Linearity Part 2


> [!INFO] Problem 4.a. 
>
> $$
> x[n] = \cos(\omega_{0}n)u[n]
> $$


> [!TIP]- TIP 4.a.1. cos, sin, and jsin
> $$
> \begin{align*}
> \cos(\omega _{0}n) &= \frac{e^{j\omega_{0}n} + e^{-j\omega_{0}n}}{2} \\
> \sin(\omega _{0}n) &= \frac{e^{j\omega_{0}n} - e^{-j\omega_{0}n}}{j2} \\
> j\sin(\omega _{0}n) &= \frac{e^{j\omega_{0}n} - e^{-j\omega_{0}n}}{2}
> \end{align*}
> $$

> [!TIP]- Tip 4.a.2 Trig Identity
> $$
> {\cos(\omega_{0}n)+j\sin(\omega_{0}n)=e^{j\omega_{0}n}}
> $$

$$
\begin{align*}
x[n] &= \cos(w_{0}n)u[n] \\

X(z)&=\frac{1}{2} \frac{1}{1-e^{j\omega_{0}}z^{-1}} + \frac{1}{2} \frac{1}{1-e^{-j\omega_{0}}z^{-1}}, & |z|>|e^{\pm j \omega_{0}}|,|z|>1 \\

&=\frac{1}{2} \frac{1-e^{-j\omega_{0}}z^{-1}+1-e^{j\omega_{0}}z^{-1}}{(1-e^{j\omega_{0}}z^{-1}) (1-e^{-j\omega_{0}}z^{-1})} \\
&=\frac{1}{2} \frac{2-2\left( \frac{e^{j\omega_{0}}+e^{-j\omega_{0}}}{2} \right)z^{-1}}{1-2\left( \frac{e^{j\omega_{0}}+e^{-j\omega_{0}}}{2} \right)z^{-1}+z^{-2}}
\end{align*}
$$


> [!WARNING] 
> I get the feeling that the reference is incomplete for this one, so I'm guessing that **this is not the final answer yet**

## Example 5 - Time Shifting


> [!INFO] Problem 5
> $$
> x[n] = \begin{cases}
> 1 & 0\leq n\leq N-1  \\
> 0 & \text{elsewhere}
> \end{cases}
> $$

$$
x[n] = \{\underbrace{\underset{\uparrow}1,1,1,\dots,1}_{0 \text{ to } N-1}\}
$$

$$
\begin{align*}
x[n]&=u[n]-u[n-N] \\
X(z)&= Z\{u[n]\}- Z\{u[n-N]\} \\
&= Z\{u[n]\}- z^{-N}Z\{u[n]\} \\
&=Z\{u[n]\}(1-z^{-N}), &\frac{1}{1-z^{-1}}\\
\end{align*}
$$

$$
\boxed{
\begin{align*}
X(z) &= \frac{1-z^{-N}}{1-z^{-1}}, &|z| > 1
\end{align*}
}
$$

## Example 6 - Scaling in the Z-Domain


> [!INFO] Problem 6.a.
> $$
> x[n] = a^n\cos(\omega_{0}n)u[n] 
> $$

$$
\begin{align*}
\text{let } x_{1}[n] &= \cos(\omega_{0}n)u[n] \\
X_{1}(z) &= \frac{1-z^{-1}\cos(\omega_{0})}{1-2z^{-1}\cos(\omega_{0})+z^{-2}}, &|z|>1
\end{align*}
$$

$$
\begin{align*}
X(z) &= X_{1}(a^{-1}z) \\
&= \frac{1-(a^{-1}z)^{-1}\cos(\omega_{0})}{1-2(a^{-1}z)\cos(\omega_{0})+(\alpha^{-1}z)^{-2}}
\end{align*}
$$

$$
\boxed{X(z)=\frac{1-az^{-1}\cos(\omega_{0})}{1-2az^{-1}\cos(\omega_{0})+a^2z^{-2}}\text{, }|z|>|a|}
$$

> [!INFO] Problem 6.b.
> $$
> x[n] = a^n\sin(\omega_{0}n)u[n] 
> $$

$$
\begin{align*}
\text{let } x_{1}[n]  &= \sin(\omega_{0}n)u[n] \\
X_{1}(z) &= \frac{z^{-1}\sin(\omega_{0})}{1-2z^{-1}\cos(\omega_{0})+z^{-2}} \text{, }|z|>1
\end{align*}
$$

$$
\begin{align*}
X(z) &= X(a^{-1}z) \\
&= \frac{(a^{-1}z)^{-1}\sin(\omega_{0})}{1-2(a^{-1}z)^{-1}\cos(\omega_{0})+(a^{-1}z)^{-2}} \text{}
\end{align*}
$$

$$
\boxed{X(z)=\frac{az^{-1}\sin(\omega_{0})}{1-2az^{-1}\cos(\omega_{0})+a^{2}z^{-2}} \text{, }|z|>|a|}
$$

## Example 8 - Differentiation in the Z-Domain

> [!INFO] Problem 8
> $$
> x[n] = na^{n}u[n]
> $$

$$
\begin{align*}
x_{1}[n] &= a^nu[n] \\
X_{1}(z) &= \frac{1}{1-az^{-1}}, &|z|>|a|
\end{align*}
$$

$$
\begin{align*}
X(z) &= (-z) \frac{d}{dz}\{X_{1}(z)\} \\
&=(-z) \frac{d}{dz}\left\{  \frac{1}{1-az^{-1}}  \right\} \\
&= -z \frac{0-(1)(0+az^{-2})}{(1-az^{-1})^2} \\
&= -z \frac{-az^{-2}}{(1-az^{-1})^2}, &|z|>|a| \\
\end{align*}
$$

$$
\boxed{
X(z) = \frac{az^{-1}}{(1-az^{-1})^2}\text{, }|z|>|a|
}
$$

## Example not in the slides 1 - Time Shifting

> [!INFO] Problem
>
> $$
> x[n] = \left( \frac{1}{2} \right)^n u[n-2]
> $$

$$
\text{let }x_{1}[n] = \left( \frac{1}{2} \right)^n u[n]\to X_{1}(z)=\frac{1}{1-\frac{1}{2}z^{-1}}
$$

$$
\begin{align*}
X(z)&= Z\left\{\left( \frac{1}{2} \right)^2 \left( \frac{1}{2} \right)^{n-2}u[n-2]\right\} \\
&=Z\left\{\frac{1}{4}\left( \frac{1}{2} \right)^{n-2} u[n-2]\right\} \\
&=\frac{1}{4}z^{-2}X_{1}(z)
\end{align*}
$$

$$
\boxed{
\begin{align*}
\frac{1}{4} \frac{z^{-2}}{1-\frac{1}{2}z^{-1}}, \text{ }|z|> \frac{1}{2}
\end{align*}
}
$$

## Example not in the slides 2 - Time Reversal


> [!INFO] Problem a
> $$
> x[n] = u[-n]
> $$

$$
\begin{align*}
x_{1}[n] &= u[n] \\
X_{1}(z) &= \frac{1}{1-z^{-1}}, &|z|>1
\end{align*}
$$

$$
\begin{align*}
X(z) &= X_{1}(z^{-1}) \\
&= \frac{1}{1-(z^{-1})^{-1}}
\end{align*}
$$

$$
\boxed{
X(z)= \frac{1}{1-z}\text{, } |z|>1 
}
$$

> [!INFO] Problem b
> $$
> x[n] = \left( \frac{1}{2} \right)^n u[-n]
> $$

$$
\begin{align*}
x_{1}[n] &= \left( \frac{1}{2} \right)^n u[-n] \\
&= 2^nu[n] \\
X_{1}(z) &= \frac{1}{1-2z^{-1}}, &|z|>2 \\
X(z) &= X_{1}(z^{-1})
\end{align*}
$$

$$
\boxed{
X(z) = \frac{1}{1-2z}\text{, }|z|< \frac{1}{2}
}
$$

## Example not in the slides 3 - Convolution of Two Sequences


> [!INFO] Problem
> $$
> \begin{align*}
> x_{1}[n] &= \{\underset{\uparrow}1,2,1\} \\
> x_{2}[n] &= \{\underset{\uparrow}1,1,1,1,1,1\}
> \end{align*}
> $$

$$
\begin{align*}
X_{1}(z)&=1+2z^{-1}+z^{-2} \\
X_{2}(z)&=1+z^{-1}+z^{-2}+z^{-3}+z^{-4}+z^{-5}\\
X(z)&=X_{1}(z)X_{2}(z) \\
&=(1+2z^{-1}+z^{-2})(1+z^{-1}+z^{-2}+z^{-3}+z^{-4}+z^{-5})
\end{align*}
$$

Perform convolution using any preferred method

$$
\boxed{
\begin{align}
X(z) &= 1+3z^{-1}+4z^{-2}+4z^{-3}+4z^{-4}+4z^{-5}+3z^{-6}+z^{-7} \\ \\
x[n] &= \{\underset{\uparrow}1,3,4,4,4,4,3,1\}
\end{align}
}
$$