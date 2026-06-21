---
title: Inverse Z-Transform
draft: false
tags:
  - DSIGPRO
date: 2026-06-18, 22:00
---

## Sources

1.  InverseZTransform (Lecture Slides & Annotations)
2. Lecture Notes

## Example 1 - Inverse z-transform


> [!INFO] Problem 1.a.
> Find the inverse z-transform of 
> $$
> X(z)=\frac{1}{1-1.5z^{-1}+0.5z^{-2}}
> $$
>
> a.)  $\text{ROC: }|z|>1$
>
> b.) $\text{ROC: }|z|<0.5$
>
> c.) $\text{ROC: }0.5<|z|<1$

Positive power of $z$

$$
\begin{align*}
X(z)&=\frac{1}{1-1.5z^{-1}+0.5z^{-2}} \cdot \frac{z^2}{z^2} \\
&= \frac{z^2}{z^2-1.5z+0.5}
\end{align*}
$$

Set a side one $z$
$$
\begin{align*}
\frac{X(z)}{z} &= \frac{z}{z^2-1.5z+0.5}  \\
&= \frac{z}{(z-0.5)(z-1)} \\
\frac{X(z)}{z} &= \frac{A_{1}}{z-0.5}+\frac{A_{2}}{z-1}
\end{align*}
$$

$$
\boxed{A_{k}=(z-P_{k}) \frac{X(z)}{z} \Big|_{z=P_{k}}}
$$

$$
\begin{align*}
A_{1} &= (z-0.5) \frac{X(z)}{z} \Big|_{z=0.5} 
\\ &= (z-0.5) \frac{1}{(z-0.5)(z-1)}\Big|_{z=0.5} \\
&=\frac{z}{z-1}\Big|_{z=0.5} \\
&=-1\\
A_{2}&=(z-1) \frac{X(z)}{z} \big|_{z=1} \\
&= \frac{z}{z-0.5} \Big|_{z=1} \\
&= 2
\end{align*}
$$

$$
\begin{align*}
\frac{X(z)}{z} &= \frac{-1}{z-0.5} + \frac{2}{z-1} \\
X(z) &= \frac{-z}{z-0.5} + \frac{2z}{z-1} \\
X(z) &= \frac{-1}{1-0.5z^{-1}}+\frac{2}{1-z^{-1}}
\end{align*}
$$

### a.) ROC: |z| > 1 (Causal)

$$
\boxed{
\begin{align*}
x[n] &= -(0.5)^nu[n]+2(1)^nu[n] \\
&= -(0.5)^n u[n] + 2u[n]
\end{align*}
}
$$

### b.) ROC: |z| < 0.5 (Anticausal)

$$
\boxed{x[n]=(0.5)^nu[-n-1]-2u[-n-1]}
$$

### c.) ROC: 0.5 < |z| < 1 (Noncausal)

$$
\boxed{
x[n]= \underbrace{-(0.5)^nu[n]}_{|z|>0.5}-\underbrace{2u[-n-1]}_{|z|<1}
}
$$
