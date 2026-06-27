---
title: Inverse Z-Transform
draft: false
tags:
  - DSIGPRO
date: 2026-06-22, 22:00
---

## Sources

1.  InverseZTransform (Lecture Slides & Annotations)
2. Lecture Notes

## Example 1 - Inverse z-transform Part 1


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

## Example 2 - Inverse z-transform Part 2


> [!INFO] Problem 2
> Find the inverse z-transform of 
> $$
> X(z) = \frac{1}{(1+z^{-1})(1-z^{-1})^2}
> $$

Positive powers of $z$

$$
\begin{align*}
X(z) &= \frac{1}{(1+z^{-1})(1-z^{-1})} \cdot \frac{z^3}{z^3} \\
X(z) &= \frac{z^3}{(z+1)(z-1)^2} \\
\frac{X(z)}{z} &= \frac{z^2}{(z+1)(z-1)^2}  \\
\frac{X(z)}{z} &= \frac{A_{1}}{z+1} + \frac{A_{2}}{z-1} + \frac{A_{3}}{(z-1)^2}
\end{align*}
$$

$$
\begin{align*}
A_{1}&=(z+1) \frac{X(z)}{z}\Big|_{z=-1} \\
&= \cancel{(z+1)} \frac{z^2}{\cancel{(z+1)}(z-1)}\Big|_{z=-1} \\
&= \frac{z^2}{(z-1)^2}\Big|_{z=-1} \\
A_{1} &=\frac{1}{4}
\end{align*}
$$

$$
\begin{align*}
A_{2} &= \frac{d}{dz}\left\{(z-1)^2 \frac{X(z)}{z} \right\}\Big|_{z=1} \\
&= \frac{d}{dz}\left\{\cancel{(z-1)^2} \frac{z^2}{(z+1)(z-1)^2} \right\}\Big|_{z=1} \\
&= \frac{d}{dz}\left\{ \frac{z^2}{z+1} \right\} \Big|_{z=1} \\
&= \frac{(z+1)(2z)-z^2(1)}{(z+1)^2} \Big|_{z=1} \\
A_{2} &= \frac{3}{4}
\end{align*}
$$

$$
\begin{align*}
A_{3}&=\frac{z^2}{z+1}\Big|_{z=1} \\
A_{3}&=\frac{1}{2}
\end{align*}
$$

$$
\begin{align*}
\frac{X(z)}{z} &= \frac{1}{4} \frac{1}{z+1} + \frac{3}{4} \frac{1}{z-1} + \frac{1}{2} \frac{1}{(z-1)^2} \\
X(z) &= \frac{1}{4} \frac{z}{z+1} + \frac{3}{4} \frac{z}{z-1} + \frac{1}{2} \frac{z}{(z-1)^2} \\
&= \frac{1}{4} \frac{1}{1+z^{-1}} + \frac{3}{4} \frac{1}{1-z^{-1}} + \frac{1}{2} \frac{z}{\left( \frac{z}{z}-\frac{1}{z} \right)^2} \\
\end{align*}
$$

Consider:
$$
\frac{z}{z^2\left( \frac{z}{z} - \frac{1}{z} \right)^2} = \frac{z}{z^2\left( 1 - z^{-1} \right)^2} = \frac{z^{-1}}{(1-z^{-1})^2}
$$


> [!TIP]- Tip 2. $na^nu[n]$
> 
> $$
> na^nu[n] \longleftrightarrow \frac{az^{-1}}{(1-az^{-1})^2}\text{, }|z|>|a|
> $$

$$
z^-1 
\left\{ 
X(z) = 
\frac{1}{4} \frac{1}{1+z^{-1}} +
\frac{3}{4} \frac{1}{1-z^{-1}} +
\frac{1}{2} \frac{z^{-1}}{\left(1-z^{-1}\right)^2}
\right\}
z^-1
$$

$$
\boxed{
x(n) = 
\frac{1}{4} (-1)^n u[n] +
\frac{3}{4} u[n] +
\frac{1}{2} n u[n]
}
$$

## Example 3 - Inverse z-transform Part 2


> [!INFO] Problem 3
> Find the inverse z-transform of 
> $$
> X(z) = \frac{1+z^{-1}}{1-z^{-1}+0.5z^{-2}}
> $$

$$
\begin{array}{ccc}
M=1, \quad N=2, \quad N>M
\end{array}
$$
This is already a *proper* fraction:

Positive powers of $z$:
$$
\begin{align*}
X(z) &= \frac{z^2+z}{z^2-z+0.5} \\
\frac{X(z)}{z} &= \frac{z+1}{z^2-z+0.5} \\
&= \frac{A_{1}}{z-P_{1}} + \frac{A_{2}}{z-P_{2}}
\end{align*}
$$

$$
\begin{align*}
P_{1} &= \frac{1}{2}+\frac{j}{2} \\
P_{2} &= P_{1}^* = \frac{1}{2}-\frac{j}{2}
\end{align*}
$$

$$
\begin{align*}
\frac{X(z)}{z} &= \frac{z+1}{(z-P_{1})(z-P_{2})} \\
&= \frac{A_{1}}{z-P_{1}} + \frac{A_{2}}{z-P_{2}}
\end{align*}
$$

$$
\boxed{
\begin{align*}
A_{2} &= A_{1}^* \\
P_{2} &= P_{1}^*
\end{align*}
}
$$

$$
\begin{align*}
A_{1} &= (z-P_{1}) \frac{X(z)}{z} \Big|_{z=P_{1}} \\
&= \frac{z+1}{z-P_{2}} \Big|_{z=P_{1}} \\
&= \frac{P_{1}+1}{P_{1}-P_{2}}
\end{align*}
$$

$$
\begin{array}{cc}
A_{1} = \frac{1}{2} - j \frac{3}{2},
\quad
A_{2} =  A_{1}^* = \frac{1}{2} +j \frac{3}{2}
\end{array}
$$

$$
\begin{align*}
\frac{X(z)}{z} &= \frac{A_{1}}{z-P_{1}} + \frac{A_{1}^*}{z-P_{1}^*} \\
X(z) &= \frac{A_{1}}{1-P_{1}z^{-1}} + \frac{A_{1}^*}{1-P_{1}^{*}z^{-1}} \\
\end{align*}
$$

$$
\underline{x[n] = A_{1}(P_{1})^n u[n] + A_{1}^* (P_{1}^*)^n u[n]}
$$


> [!TIP]- $A_{K}$ and $P_K$
> $$
> \begin{align*}
> A_{K} = |A_{K}|e^{j\alpha_{K}} \\
> P_{K} = r_{K}e^{j\beta{K}}
> \end{align*}
> $$

$$
x[n] = 2|A_{K}|r_{k}^n\cos( \underbrace{\beta_{K}n}_{45^\circ n \text{ or} \frac{\pi}{4}n}+\alpha_{K})
$$

if $k=1$

$$
\begin{align*}
A_{1} &=\frac{1}{2} - j \frac{3}{2} = \frac{\sqrt{ 10 }}{2}e^{-j71.57^\circ} \\
P_{1} &= \frac{1}{2} + j \frac{1}{2} = \frac{1}{\sqrt{ 2 }}e^{j\frac{\pi}{4}}
\end{align*}
$$

$$
\begin{align*}
x[n] &= 2\left( \frac{\sqrt{ 10 }}{2} \right)\left( \frac{1}{\sqrt{ 2 }} \right)^n \cos\left( \frac{\pi}{4} n - 71.57^\circ \right)u[n] \\
\end{align*}
$$
$$
\boxed{
x[n] = \sqrt{ 10 }\left( \frac{1}{\sqrt{ 2 }} \right)^n \cos\left( \frac{\pi}{4}n - 71.57^\circ \right)u[n]
}
$$
## Example 4 - Time Shifting Property

> [!INFO] Problem 4
> $$
> x_{1}[n] = x[n-2]
> $$

$$
\begin{align*}
X_{1}^+(z) = z^{-2}X_{1}^{+}(z) + x_{1}[-1]z^{-1} + x[-2]
\end{align*}
$$


> [!TIP]- Tip 4. $x[n]$ and $x^+(z)$
> 
> $$
> \begin{align*}
> x[n] &= a^n \\
> X^+(z) &= \frac{1}{1-az^{-1}}
> \end{align*}
> $$


$$
\boxed{X^{+}(z) = \frac{z^{-2}}{1-az^{-1}}+a^{-1}z^{-1}+a^{-2}}
$$

## Example 5 - Using Z-Transform to Solve an LCCDE


> [!INFO] Problem
> $$
> y[n] = \frac{3}{5} y[n-1] - \frac{2}{25} y[n-2] + x[n-1] + \frac{1}{2}x[n-2]
> $$
> 
> 
> Find:
> 	
> 1. The impulse response
> 
> 2. The zero-state step response
> 
> 3. The step response if $y[-1]=1$ and $y[n-2]=2$.

Take the one-sided $z$-transform of both sides

$$
\begin{align*}
Y^+(z) &= \frac{3}{5} \left\{ z^{-1}Y^+(z)+y[-1] \right\} - \frac{2}{25} \left\{ z^{-2}Y^+(z)+y[-1]z^{-1}+y[-2] \right\} + \{z^{-1}X^+(z)+x[-1]\} + \frac{1}{2} \{z^{-2}X^+(z)+x[-1]z^{-1}+x[-2]\} \\

\left( 1-\frac{3}{5}z^{-1}+\frac{2}{25}z^{-2} \right)Y^+(z) &= \frac{3}{5}y[-1]-\frac{2}{25}y[-1]z^{-1}-\frac{2}{25}y[-2]+\left( z^{-1}+\frac{1}{2}z^{-2} \right)x^+(z)+x[-1]+\frac{1}{2}x[-1]z^{-1}+\frac{1}{2}x[-2]
\end{align*}
$$

### 5.1. Impulse Response

$h[n]$:

$$
\begin{align*}
\text{Input}&: x[n] = \delta[n] \\
\text{Initial conditions}&: y[-1] = y[-2] = 0
\end{align*}
$$

$$
\begin{align*}
\left( 1-\frac{3}{5}z^{-1}+\frac{2}{25}z^{-2}\right)Y^+(z) &= \left( z^{-1}+\frac{1}{2}z^{-2}  \right)X^{+}(z) \\

H(z) &= \frac{Y^+(z)}{X^+(z)} = \frac{z^{-1}+\frac{1}{2}z^{-2}}{1-\frac{3}{5}z^{-1}+\frac{2}{25}z^{-2}}
\end{align*}
$$

Perform the following long division:

$$
\frac{2}{25}z^{-2} - \frac{3}{5} z^{-1} + 1 \overline{\Big)\frac{1}{2}z^{-2}+z^{-1}}

$$

Resulting in $\frac{19}{4}z^{-1}-\frac{25}{4}$

$$
H(z) = \frac{25}{4} + \frac{
\displaystyle \frac{19}{4}z^{-1}-\frac{25}{4}
}{
\displaystyle 1 - \frac{3}{5}z^{-1}+\frac{2}{25}z^{-2}
}
$$

Consider:

$$
\begin{align*}
H_{1}(z) &= \frac{
\displaystyle \frac{19}{4}z^{-1}-\frac{25}{4}
}{
\displaystyle 1 - \frac{3}{5}z^{-1}+\frac{2}{25}z^{-2}
} \cdot \frac{z^2}{z^2} \\
\frac{H_{1}(z)}{z} &= \frac{\frac{19}{4}-\frac{25}{4}z}{\left( z-\frac{1}{5} \right)\left( z-\frac{2}{5} \right)}= \frac{A_{1}}{z-\frac{1}{5}}+\frac{A_{2}}{z-\frac{2}{5}} \\
A_{1}&= \frac{\frac{19}{4}-\frac{25}{4}z}{z-\frac{2}{5}}\Big|_{z=\frac{1}{5}} =-\frac{35}{2} \\
A_{2} &= \frac{\frac{19}{4}-\frac{25}{4}z}{z-\frac{1}{5}}\Big|_{z=\frac{2}{5}}=\frac{45}{4}\\
H_{1}(z)&=-\frac{35}{2} \frac{1}{1-\frac{1}{5}z^{_{-1}}} + \frac{45}{4} \frac{1}{1-\frac{2}{5}z^{-1}}\\
H(z)&= \frac{25}{4}- \frac{35}{2} \frac{1}{1-\frac{1}{5}z^{-1}}+\frac{45}{4} \frac{1}{1-\frac{2}{5}z^{-1}}
\end{align*} 
$$
$$
\boxed{
h[n] = \frac{25}{4} \delta[n] - \frac{35}{2}\left( \frac{1}{5} \right)^n u[n] + \frac{45}{4}\left( \frac{2}{5} \right)^n u[n]
}
$$
### 5.2. Zero-State Step Response

$$
\begin{align*}
x[n] &= u[n] \\
\text{zero state: }y[-1] &= y[-2] =0
\end{align*}
$$

$$
\begin{align*}
x^+(z) &= z^+\{u[n]\} \\
&= \frac{1}{1-z^{-1}}
\end{align*}
$$

$$
\begin{align*}
Y^+(z)\left( 1-\frac{3}{5}z^{-1}+\frac{2}{25}z^{-2} \right) &=\left( \frac{1}{2} z^{-2} + z^{-1} \right)X^+(z) \\

Y^{+}(z)\left( 1-\frac{3}{5}z^{-1} + \frac{2}{25}z^{-2} \right) &= \left( \frac{1}{2}z^{-2}+z^{-1} \right)\left( \frac{1}{1-z^{-1}} \right) \\
Y^+(z) &= \frac{\frac{1}{2}z^{-2}+z^{-1}}{\left( 1-\frac{3}{5}z^{-1} + \frac{2}{25} z^{-2} \right)(1-z^{-1})} \cdot \frac{z^3}{z^3} \\
&= \frac{\frac{1}{2}z+z^2}{\left( z^2-\frac{3}{5}z+\frac{2}{25} \right)(z-1)}\\
\frac{Y^+(z)}{z} &= \frac{z+\frac{1}{2}}{\left( z-\frac{1}{5} \right)\left( z-\frac{2}{5} \right)(z-1)} \\
&= \frac{A_{1}}{z-\frac{1}{5}} + \frac{A_{2}}{z-\frac{2}{5}} + \frac{A_{3}}{z-1}
\end{align*}
$$

$$
\begin{align*}
A_{1} &= \frac{z+\frac{1}{2}}{\left( z-\frac{2}{5} \right)(z-1)}\Big|_{z=\frac{1}{5}} = \frac{35}{8} \\

A_{2} &= \frac{z+\frac{1}{2}}{\left( z-\frac{1}{5} \right)(z-1)}\Big|_{z=\frac{2}{5}} = -\frac{15}{2} \\

A_{3} &= \frac{z+\frac{1}{2}}{\left( z-\frac{1}{5} \right)\left( z-\frac{2}{5} \right)}\big|_{z=1}=\frac{25}{8}
\end{align*}
$$

$$
\begin{align*}
Y^+(z) &= \frac{35}{8} \frac{1}{1-\frac{1}{5}z^{-1}} - \frac{15}{2} \frac{1}{1-\frac{2}{5}z^{-1}} + \frac{25}{8} \frac{1}{1-z^{-1}}
\end{align*}
$$
$$
\boxed {
y[n] = \frac{35}{8}\left( \frac{1}{5} \right)^n u[n] - \frac{15}{2} \left( \frac{2}{5} \right)^n u[n] + \frac{25}{8} u[n]
}
$$

### 5.3. Zero-State Step Response

$$
\begin{array}{ccc}
x[n] = u[n] \quad y[-1] = 1 \quad y[-2] = 2
\end{array}
$$
$$
\begin{align*}
Y^+(z)\left( 1-\frac{3}{5}z^{-1} + \frac{2}{25}z^{-2}\right) &= \frac{3}{5}(1) - \frac{2}{25} (1)z^{-1} - \frac{2}{25} (2) + \left( \frac{1}{2}z^{-2} + z^-1 \right)\left( \frac{1}{1-z^{-1}} \right) \\

&= \frac{\left( \frac{11}{25}-\frac{2}{25}z^{-1} \right)(1-z^{-1})+\frac{1}{2}z^{-2}+z^{-1}}{(1-z^{-1})} \\
Y^+(z) &= \frac{\frac{11}{25}+\frac{34}{25}z^{-1}+\frac{29}{50}z^{-2}}{\left( 1-\frac{3}{5}z^{-1}+\frac{2}{25}z^{-2} \right)(1-z^{-1})} \cdot \frac{z^3}{z^3}\\

&=\frac{\frac{11}{25}z^3+\frac{34}{25}z^2+\frac{29}{50}z}{\left( z-\frac{1}{5} \right)\left( z-\frac{2}{5} \right)(z-1)}\\
\frac{Y^+(z)}{z} &= \frac{A_{1}}{z-\frac{1}{5}}+ \frac{A_{2}}{z-\frac{2}{5}}+ \frac{A_{3}}{z-1}
\end{align*}
$$

$$
\begin{array}{ccc}
A_{1}=\frac{1087}{200} \quad A_{2}=-\frac{1493}{150} \quad A_{3} = \frac{119}{24}
\end{array}
$$

$$
\boxed{
y[n] = \left[ \frac{1087}{200}\left( \frac{1}{5} \right)^n - \frac{1493}{150} \left( \frac{2}{5} \right)^n + \frac{119}{24} \right] u[n]
}
$$
## Example not in the slides - Time Shifting Property


> [!INFO] Problem 
> $$
> x[n-2]= x^+(z)+\sum^2_{n=1}x[-n]z^{n}
> $$

$$
\begin{align*}
z^+ \left\{x[n-2]\right\} &= z^{-2}\left\{X^+(z)+\sum^2_{n=1}x[-n]z^{n}\right\} \\
&= z^{-2} \left\{X^+(z) + x[-1]z + x[-2]z^2 \right\} \\
&=z^{-2}X^+(z)+X[-1]z^{-1}+x[-2]
\end{align*}
$$

$$
\begin{align*}
z^+{x[n-2]} &= z^{-2}x^+(z)+x[-1]+x[-2] \\
z^+{x[n-1]} &= z^{-1}x^+(z)+x[-1] \\
z^+{x[n-3]} &= z^{-3}x^+(z) + x[-1]z^{-2} + x[-2]z^{-1} + x[-3]
\end{align*}
$$