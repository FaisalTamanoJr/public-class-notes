---
title: Discrete Time Fourier Transform (DTFT)
draft: false
tags:
  - DSIGPRO
date: 2026-07-15, 15:00
---

## Sources

1. Lecture Notes 
2. Lecture Pages (Module 8 Discrete-time Fourier Transform)

## Check Your Understanding


> [!INFO] Problem a.
> Solve for the DTFT of the following signal:
> 
> $$
> x[n] = u[n] - u[n-6]
> $$

$$
\begin{align*}
x[n] &= 1, &&0\leq n\leq5 \\
x[n] &= \{\underset{\uparrow}1,1,1,1,1,1\} \\
X(\omega) &= \sum^\infty_{n=-\infty}x[n]e^{-j\omega n} \\
X(\omega) &= \sum^5_{n=0}(1)e^{-j\omega n} \\
X(\omega) &= 1 + e^{-j\omega} + e^{-j2\omega} + e^{-j3\omega} + e^{-j4\omega} + e^{-j5\omega}
\end{align*}
$$

> [!TIP]- $a^n$
> $$
> \sum^N_{n=0}a^n=\frac{1-a^{N+1}}{1-a}\Big|a=e^{-j\omega}
> $$

$$
\begin{align*}
X(\omega)&=\frac{1-(e^{-j\omega})^{6}}{1-(e^{-j\omega})} \\
&=\boxed{\frac{1-e^{-j6\omega}}{1-e^{-j\omega}}}
\end{align*}
$$


> [!INFO] Problem b.
> Solve for the DTFT of the following signal:
> $$
> x[n] = 2^n u[-n]
> $$

$$
\begin{align*}
x[-n]&=2^{-n}u[n] \\
x[-n]&=\frac{1}{2}^{n}u[n] \\
X_{1}(\omega) &= \frac{1}{1-\frac{1}{2}e^{-j\omega}} \\
X(\omega) &= X_{1}(-\omega) \\
X(\omega)&= \boxed{\frac{1}{1-\frac{1}{2}e^{j\omega}}}
\end{align*}
$$

> [!INFO] Problem c.
> Solve for the DTFT of the following signal:
> $$
> x[n] = \left( \frac{1}{4} \right)^n[n+4]
> $$

$$
\begin{align*}
x[n] &= \left( \frac{1}{4} \right)^{-4} \left( \frac{1}{4} \right)^{n+4} u[n+4] \\
x[n] &= 256 \left( \frac{1}{4} \right)^{n+4} u[n+4] \\
x(z) &= 256 z^{4} Z\left\{\left( \frac{1}{4} \right)^{n} u[n]\right\} \\
&= \frac{256z^{4}}{1-\frac{1}{4}z^{-1}} \\
z&=e^{j\omega} \\
X(e^{j\omega}) &= \boxed{\frac{256e^{j4\omega}}{1-\frac{1}{4}e^{-j\omega}}}
\end{align*}
$$

> [!INFO] Problem d.
> Solve for the DTFT of the following signal:
> $$
> \begin{align*}
> x[n] = \alpha^n\sin(\omega_{0}n)u[n], &&|\alpha|<1
> \end{align*}
> $$

$$
\begin{align*}
X(z) &= \frac{\alpha z^{-1}\sin(\omega_{0})}{1-2\alpha z^{-1}\cos \omega_{0}+\alpha^2z^{-2}} \\
z&=e^{j\omega} \\
X(\omega) &= \boxed{\frac{\alpha e^{-j\omega}\sin(\omega_{0})}{1-2\alpha e^{-j\omega}\cos \omega_{0}+\alpha^2e^{-j2\omega}}}
\end{align*}
$$

> [!INFO] Problem e.
> Solve for the DTFT of the following signal:
> $$
> x[n] = \{-2,1,\underset{\uparrow}0,1,2\}
> $$

$$
\boxed{X(\omega) = -2e^{j2\omega}+e^{j\omega}+e^{-j\omega}+e^{-j2\omega}}
$$

## Example 10


> [!INFO] Problem
> Determine the magnitude spectrum and phase spectrum of the following signal:
>
> $$
> \begin{align*}
> x[n] = \alpha^nu[n], &&|\alpha|<1
> \end{align*}
> $$
>
> Find the DTFT and sketch both magnitude spectrum $|X(\omega)|$ and phase spectrum $\angle X(\omega)$

TODO

## Example 11


> [!INFO] Problem
> $$
> \begin{align*}
> x[n] = a^{n}u[n], &&-1<\alpha<1
> \end{align*}
> $$
> 
> - Find the DTFT
> - Find the Energy Density Spectrum $S_{xx}(\omega)=|X(\omega)|^2$
> - Sketch the Energy Density Spectrum
> - Identify frequencies in which majority of the signal is concentrated

TODO