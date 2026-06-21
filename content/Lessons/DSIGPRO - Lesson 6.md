---
title: Rational Z-Transform and Transfer Function
draft: false
tags:
  - DSIGPRO
date: 2026-06-18, 21:45
---

## Sources

1.  Rational Z-Transform and Transfer Function (Lecture Slides)
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
&= \frac{1-(az^{-1})^M}{1-az^{-1}}
\end{align*}
$$


> [!WARNING] 
> I get the feeling that the reference is incomplete for this one, so I'm guessing that **this is not the final answer yet**

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

***

Testing graphs (ignore):

```tikz
\begin{document}
  \begin{tikzpicture}[domain=0:4]
    \draw[very thin,color=gray] (-0.1,-1.1) grid (3.9,3.9);
    \draw[->] (-0.2,0) -- (4.2,0) node[right] {$x$};
    \draw[->] (0,-1.2) -- (0,4.2) node[above] {$f(x)$};
    \draw[color=red]    plot (\x,\x)             node[right] {$f(x) =x$};
    \draw[color=blue]   plot (\x,{sin(\x r)})    node[right] {$f(x) = \sin x$};
    \draw[color=orange] plot (\x,{0.05*exp(\x)}) node[right] {$f(x) = \frac{1}{20} \mathrm e^x$};
  \end{tikzpicture}
\end{document}
```

