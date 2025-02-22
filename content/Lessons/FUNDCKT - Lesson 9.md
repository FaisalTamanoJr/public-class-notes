---
draft: false
tags: [FUNDCKT]
title: Sinusoids and Phasors
date: 2024-08-04, 20:04
---

> [!INFO]- Keywords
> [[period]], [[phase]], [[cyclic frequency]], [[out of phase]], [[in phase]], [[phasor]], [[complex number]], [[rectangular form]], [[polar form]], [[instantaneous domain representation]], [[time domain representation]], [[phasor domain representation]], [[frequency domain representation]], [[impedance]], [[reactance]], [[admittance]], [[susceptance]], [[siemens]]

> [!INFO]- Related Concepts
> [[conductance]], [[sinusoidal|sinusoid]], [[alternating current]], [[wye-delta transformations]], [[Kirchhoff’s law]], [[Kirchhoff’s Voltage Law]], [[Kirchhoff’s Current Law]], [[resistance]], [[series resistors]], [[parallel resistors]]

## Introduction

AC circuits are driven by sinusoidally time-varying voltage or currents. There are three reasons why they are valuable:

1. They are sinusoidal, and, as such, they are easier to manage mathematically.
2. They are the most dominant form of signal in the communications and electric power industries because of how easy they are to generate and transmit.
3. They are useful for periodic signal analysis—the sum of sinusoids can represent practical periodic signals.

## Sinusoids

$$
v(t)=V_{m}\sin\omega t \to v(t) = V_{m} \sin(\omega t+\phi)
$$

where

$$
\begin{align} \\
V_{m}&=\text{sinusoid amplitude} \\
\omega&=\text{sinusoid angular frequency (in radians)} \\
\omega t&=\text{sinusoid argument} \\
\phi&=\text{phase}
\end{align}
$$

Because the sinusoid repeats at every $T$ seconds, the $T$ is referred to as the *period* of the sinusoid and is equivalent to

$$
T=\frac{2\pi}{\omega}
$$

Because it repeats itself at every $T$ seconds, it satisfies the rule in which $f(t)=f(t+nT)$ (since it is sinusoidal); this is a characteristic of a *periodic function*.

The seconds per cycle is called a period ($T$), while cycles per second is called the *cyclic frequency* (in Hz). This is represented as

$$
f=\frac{1}{T}
$$

If there are two voltage, let’s say $v_{1}$ and $v_{2}$, and

$$
\begin{align}
v_{1}(t)=V_{m}\sin\omega t && v_{2}(t)=V_{m}\sin(\omega t+\phi)
\end{align}
$$

if $v_{2}$ occurs first before $v_{1}$ in time, we say that it leads by $\phi$, and $v_{1}$ lags by $\phi$. If $\phi\neq{0}$, then we say that they are *out of phase*; else, they are *in phase*.

We can express and transform sinusoids into either sin or cosine form using the following identities:

$$
\begin{align}
\sin(\omega t\pm180^{\circ})=-\sin\omega t \\
\cos(\omega t\pm180^{\circ})=-\cos\omega t \\
\sin(\omega t\pm90^{\circ})= \pm\cos\omega t \\
\cos(\omega t\pm90^{\circ})= \mp\sin\omega t \\
\end{align}
$$

We could use a *graphical approach* to relate/compare sinusoids. In this approach, the horizontal axis pertains to the cosine’s magnitude, while the vertical one pertains to the sine’s magnitude. Additionally, angles are measured positively when they are counterclockwise from the horizontal, while negatively when they are clockwise from the horizontal. To obtain the sum of two sinusoids with the same frequency, we can use the formulas below

$$
\begin{gather}
A\cos\omega t +B\sin\omega t = C\cos(\omega t - \theta) \\ \\
C=\sqrt{ A^2+B^2 }, \quad \quad \theta=\tan^{-1}{\frac{B}{A}}
\end{gather}
$$

> [!WARNING]
> Although the positive direction for the vertical axis usually points up, it points down for this case.

## Phasors

Besides sine or cosines, we can also conveniently express sinusoids using a *phasor*—a complex number representing the sinusoid’s phase and amplitude. An important concept in understanding phasors are complex numbers; they can be written in either rectangular or polar form. The rectangular form of a complex number $z$ is represented as

$$
z=x+jy
$$

where $j=\sqrt{ -1 }$ ; $x$ is the real component; $y$ is the imaginary component of $z$. All relevant forms of $z$ is shown in the table below,

| Form             | Expression      |
| ---------------- | --------------- |
| Rectangular Form | $z=x+jy$        |
| Polar form       | $z=r\angle\phi$ |
| Exponential form | $z=re^{j\phi}$  |

The $z$ may also be written as

$$
z=x+jy=r\angle\phi=r(\cos \phi+j\sin \phi)
$$

> [!Example]- Performing Various Operations Using the Different Forms of Complex Numbers
>
> | Operation         | Formula                                                                         |
> | ----------------- | ------------------------------------------------------------------------------- |
> | Subtraction       | $z_{1}-z_{2}=(x_{1}-x_{2})+j(y_{1}-y_{2})$                                      |
> | Multiplication    | $z_{1}z_{2}=r_{1}r_{2}\angle(\phi_{1}+\phi_{2})$                                |
> | Division          | $\displaystyle\frac{z_{1}}{z_{2}}=\frac{r_{1}}{r_{2}}\angle(\phi_{1}-\phi_{2})$ |
> | Reciprocal        | $\displaystyle\frac{1}{z}=\frac{1}{r}\angle-\phi$                               |
> | Square Root       | $\sqrt{ z }=\sqrt{ r }\angle(\phi/2)$                                           |
> | Complex Conjugate | $z^{\displaystyle *}=x-jy=r\angle-\phi=re^{-j\phi}$                             |

The component of the complex number $z$,

$$
e^{\pm j\phi}=\cos \phi\pm j\sin \phi
$$

has two parts: the real part, and the imaginary part. The real part is represented as $\mathrm{Re}(e^{j\phi})$, while the imaginary part is represented as $\mathrm{\mathrm{Im}}(e^{j\phi})$, as seen in the following equations:

$$
\begin{align}
\cos \phi&=\mathrm{Re}(e^{j\phi}) \\
\sin \phi&=\mathrm{\mathrm{Im}}(e^{j\phi})
\end{align}
$$

$V$ is the phasor representation of $v(t)$. The standard convention of representing the sinusoid with a phasor is to use the real part, thus,

$$
\boldsymbol{V}=\mathrm{Re}(Ve^{j\omega t})
$$

Because $e^{j\omega t}$ is always implicitly present when the sinusoid is expressed as a phasor, it is important to remember that $\omega$ is the frequency of the phasor. Furthermore, we can obtain the sinusoid of a given phasor $V$ by multiplying it with $e^{j\omega t}$ and taking the real part. Conversely, we can take the phasor corresponding to a sinusoid by expressing it in cosine form (for the real part of the complex form), and taking out the time factor $e^{j\omega t}$. To summarize,

$$
\begin{align}
v(t)=V_{m}\cos(\omega t+\phi) && \Leftrightarrow && \boldsymbol{V}=V_{m}\angle\phi
\end{align}
$$

> [!NOTE]
> 1. $v(t)=V_{m}\cos(\omega t+\phi)=\mathrm{Re}(V_{m}e^{j(\omega t)+\phi})$
> 2. Italic letters are used to represent complex numbers, while bold letters are used to represent phaosrs
> 3. $j=1\angle90$

> [!SUMMARY] Sinusoid-Phasor Transformation Table
>
> | Time domain representation   | Phasor domain representation |
> | ---------------------------- | ---------------------------- |
> | $V_{m}\cos(\omega t+\phi)$   | $V_{m}\angle\phi$            |
> | $V_{m}\sin(\omega t+\phi)$   | $V_{m}\angle(\phi-90)$       |
> | $I_{m}\cos(\omega t+\theta)$ | $I_{m}\angle\theta$          |
> | $I_{m}\sin(\omega t+\theta)$ | $I_{m}\angle(\theta-90)$     |

Differentiating a sinusoid is equivalent to multiplying its corresponding phasor with $j\omega$.

$$
\begin{align}
\frac{dv}{dt} && \Leftrightarrow && jw\boldsymbol{V}
\end{align}
$$

In contrary, integrating a sinusoid is equivalent to dividing its corresponding phasor with $j\omega$.

$$
\begin{align}
\int v dt && \Leftrightarrow && \frac{\boldsymbol{V}}{j\omega}
\end{align}
$$

These two equations are helpful for finding the steady-state solution without the initial values of the variables involved.

Besides this, phasors are also useful for adding sinusoids with the same frequency: it is equal to the sum of their corresponding phasors.

> [!SUMMARY] Key Differences between $v(t)$ and $\boldsymbol{V}$:
> 1. $v(t)$ is the *instantaneous* or *time domain representation*; $\boldsymbol{V}$ is the *frequency* or *phasor domain representation*.
> 2. $v(t)$ is time dependent; $\boldsymbol{V}$ isn’t.
> 3. $v(t)$ is real; $\boldsymbol{V}$ is complex.
> 4. Phasor analysis is only applicable when the frequency is constant—the sinusoidal signals have the same frequency.

## Phasor Relationships for Circuit Elements

The table below summarizes the phasor relationship for the circuit elements $R, L,$ and $C$.

| Element | Time Domain         | Frequency Domain                                                                    |
| ------- | ------------------- | ----------------------------------------------------------------------------------- |
| $R$     | $v=Ri$              | $\boldsymbol{V} = R\boldsymbol{I}$                                                  |
| $L$     | $v=L \frac{di}{dt}$ | <br>$\boldsymbol{V} = j\omega L\boldsymbol{I}$                                      |
| $C$     | $i=C \frac{dv}{dt}$ | <br>$\boldsymbol{V} = \frac{\displaystyle \boldsymbol{I}}{\displaystyle j\omega C}$ |

## Impedance and Admittance

$\boldsymbol{Z}$ is a frequency-dependent quantity known as *impedance* and is measured in ohms ($\Omega$). It represents the circuit’s resistance to the sinusoidal current’s flow; nonetheless, it does not correspond to a sinusoidally varying quantity, and, thus, is not a phasor.

$$
\boldsymbol{Z}=\frac{V}{I}
$$

The table below summarizes the impedances and admittances—reciprocals of impedances—of passive elements.

| Element | Impedance                                                        | Admittance                                                      |
| ------- | ---------------------------------------------------------------- | --------------------------------------------------------------- |
| $R$     | $\boldsymbol{Z}=R$                                               | $\boldsymbol{Y}=\frac{1}{R}$                                    |
| $L$     | $\boldsymbol{Z}=j\omega L$                                       | $\boldsymbol{Y}=\frac{\displaystyle1}{\displaystyle j\omega L}$ |
| $C$     | $\boldsymbol{Z}=\frac{\displaystyle 1}{\displaystyle j\omega C}$ | $\boldsymbol{Y}=j\omega C$                                      |

> [!SUMMARY] Behavior of Impedance in Relation to the Angular Frequency
>
> | Element     | $w=0$ (for dc sources)            | $w\to \infty$ (for high frequencies) |
> | ----------- | --------------------------------- | ------------------------------------ |
> | Inductance  | $Z_{L}=0$  (short circuit)        | $Z_{L} \to \infty$  (open circuit)   |
> | Capacitance | $Z_{C}\to \infty$  (open circuit) | $Z_{C} = 0$ (short circuit)          |

The impedance can be expressed in the rectangular form

$$
\boldsymbol{Z}=R\pm jX
$$

where $R=\mathrm{Re}\boldsymbol{Z}$ and $X=\mathrm{Im}\boldsymbol{Z}$. In other words, the *resistance* is equal to the real part of the impedance, while the *reactance* is equal to the imaginary part of the impedance.

The $j$ is associated with the inductance, while $-j$ is associated with the capacitance, hence

| Formula               | Characteristic                                |
| --------------------- | --------------------------------------------- |
| $\boldsymbol{Z}=R+jX$ | inductive or lagging (current lags voltage)   |
| $\boldsymbol{Z}=R-jX$ | capacitive or leading (current leads voltage) |

In polar form, the magnitude is expressed in its absolute form (always positive).

The admittance, unlike the impedance, is expressed as

$$
\boldsymbol{Y}=G+jB
$$

where $G=\mathrm{Re}\boldsymbol{Y}$ and $B=\mathrm{Im}\boldsymbol{Y}$. Therefore, $G$ or the *conductance* is the real part of admittance, while $B$ or the *susceptance* is the imaginary part of the admittance. These three are all expressed in *siements* ($S$).

## Kirchoff’s Laws in the Frequency Domain

*Kirchoff’s current and voltage law* also applies to phasors, hence

$$
\begin{align}
\boldsymbol{V}_{1}+\boldsymbol{V}_{2}+\dots+\boldsymbol{V}_{n}=0 \\ \\
\boldsymbol{I}_{1}+\boldsymbol{I}_{2}+\dots+\boldsymbol{I}_{n}=0
\end{align}
$$

For this reason, we can also apply impedance combination, nodal and mesh analysis, superposition, and source transformation.

## Impedance Combinations

Impedance in AC circuits acts like resistance. For example,

$$
\begin{align}
\text{In series:} && Z_{eq}&=Z_{1}+Z_{2}+\dots+Z_{N}\\
\text{In parallel:} && Z_{eq}&=\left( \frac{1}{Z_{1}} +\frac{1}{Z_{2}} + \dots +\frac{1}{Z_{N}} \right)^{-1}\\
\end{align}
$$

As a result, *voltage-division principle*, *current-division princple*, *delta-to-wye* transformations, and *wye-to-delta* transformations—which was discussed previously for dc circuit analysis—are also valid for impedances.

## Sources

1. Fundamentals of Electric Circuits by Charles K. Alexander and Matthew N.O. Sadiku (Chapter 9)
