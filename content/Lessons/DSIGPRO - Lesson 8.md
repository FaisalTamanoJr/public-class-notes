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

\begin{align*}
X(\omega) &= -2e^{j2\omega}+e^{j\omega}+e^{-j\omega}+2e^{-j2\omega} \\
&=  -2 (e^{j2\omega}-e^{-j2\omega})+e^{j\omega}+e^{-j\omega}\\
&=  (j2)(-2) \left(\frac{e^{j2\omega}-e^{-j2\omega}}{j2}\right) + 2\left(\frac{e^{j\omega}+e^{-j\omega}}{2}\right) \\
&=-j4\sin(2\omega)+2\cos \omega
\end{align*}
$$

$$
\boxed{X(\omega)=2\cos \omega-j4\sin(2\omega)}
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

$$
\begin{align*}
X(\omega) &= \frac{1}{1-\alpha e^{-j\omega}} \\
&= \frac{1}{1-\alpha(\cos \omega-j\sin \omega)} \\
&= \frac{1}{(1-\alpha \cos \omega)+j\alpha \sin \omega}
\end{align*}
$$

$$
\begin{align*}
|z|&=|a+jb| \\
&=\sqrt{ a^2+b^2 }
\end{align*}
$$


> [!TIP]- Tip 10. $j^2$
> $$
> \begin{align*}
> j&=\sqrt{ -1 }\\
> j^2&=-1
> \end{align*}
> $$


$$
\begin{align*}
z &=\frac{1}{a+jb}\cdot \frac{a-jb}{a-jb} \\
z &= \frac{a-jb}{a^2-j^2b^2}=\frac{a-jb}{a^2+b^2} \\
|z| &= \frac{1}{a^2+b^2} |a-jb| \\
&= \frac{1}{a^2+b^2}\sqrt{ a^2+b^2 } \\
|z| &= \frac{1}{\sqrt{ a^2+b^2 }}
\end{align*}
$$

Magnitude:

$$
|X|(\omega)| = \frac{1}{\sqrt{ (1-\alpha \cos \omega)^2 + (\alpha \sin \omega)^2}}
$$

$$
\begin{align*}
|X(\omega)| &= \frac{1}{\sqrt{ 1-2\alpha \cos \omega+\alpha^2 }} \\
\text{at }\omega&=0: \\
|X(\omega)|&= \frac{1}{\sqrt{ 1-2\alpha+\alpha^2 }}=\frac{1}{\sqrt{ (1-\alpha)^2 }}=\frac{1}{1-\alpha}\\
\text{at }\omega&=\pi: \\
|X(\omega)|&= \frac{1}{\sqrt{ 1+2\alpha+\alpha^2 }}=\frac{1}{/\sqrt{ (1+\alpha) }}=\frac{1}{1+\alpha}
\end{align*}
$$

Phase:

$$
\begin{align*}
z &= \frac{1}{\alpha+jb}\\
\angle z &= \tan^{-1}\left( \frac{b}{a} \right) \\ 
X(\omega)&= \frac{1}{(1-\alpha \cos \omega)+j\alpha \sin \omega}  \\
\phi(\omega) &= -\tan^{-1}\left( \frac{\alpha \sin \omega}{1-\alpha \cos \omega} \right)
\end{align*}
$$

$$
\begin{align*}
\omega=0 \\
\phi(\omega)=0
\end{align*}
$$

$$
\begin{align*}
\omega=\pi \\
\phi(\omega)=0
\end{align*}
$$

$$
\begin{align*}
\omega &= \frac{\pi}{2} \\
\phi(u) &= \tan^{-1}\left( \frac{\alpha-1}{1-\alpha(0)} \right)=\tan^{-1}(\alpha)
\end{align*}
$$

$$
\begin{align*}
\omega&=\frac{3\pi}{2} \\
\phi(\omega) &= -\tan^{-1}\left( \frac{\alpha(-1)}{1-\alpha} \right)\\
&=-\tan^{-1}(-\alpha)\\
\phi(\omega)&=\boxed{\tan^{-1}(\alpha)}
\end{align*}
$$

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

$$
\begin{align*}
X(\omega) &= \frac{1}{(1-\alpha\cos \omega)+j\alpha \sin \omega} \\
|X(\omega)| &= \frac{1}{\sqrt{ (1-\alpha \cos \omega)^2+a^2\sin^2\omega }} \\
|X(\omega)|^2 &= \frac{1}{1-2 \alpha\cos \omega + \alpha^2} \\
\end{align*}
$$

$$
\begin{align*}
e.g. x[n] &=(0.5)^nu[n] \\
\alpha &=0.5 \\
|X(\omega)|^2 &= \frac{1}{1-2 (0.5)\cos \omega + 0.25} \\
\end{align*}
$$

$$
\begin{align*}
S_{xx}(\omega)  &= |X(\omega)|^2 = \frac{1}{1-\cos \omega+0.25} \\
\text{At }w=0\\
S_{xx}(0) &=4 \\
\text{At }w=\frac{\pi}{2}\\
S_{xx}\left( \frac{\pi}{2} \right) &=0.8 \\
\text{At }w=\pi\\
Sxx(\pi) &= 0.44\bar{4}
\end{align*}
$$

