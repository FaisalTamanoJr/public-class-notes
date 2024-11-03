---
draft: false
tags: [FEECONS]
title: General Second Order Systems
date: 2024-11-03, 21:03
---

## Sources

1. General Second Order EK2. (Lecture Slides)

## General Second Order Transfer Function

$\displaystyle G(s) = \frac{\omega_{n}^2}{s^2+2\zeta\omega_{n}s+\omega_{n}^2}$

Where

- $a=2\zeta\omega_{n}$
 - $\omega_{n}=\sqrt{ b }$
- $\displaystyle \zeta=\frac{a}{2\sqrt{ b }}$

## Type of Response

### Determining the Poles and Step Response Given the Damping Ratio

| Damping Ratio | Poles                                             | Step Response     |
| ------------- | ------------------------------------------------- | ----------------- |
| $\zeta=0$     | $\pm j\omega_{n}$                                 | Undamped          |
| $0<\zeta<1$   | $\pm j\omega_{n}\sqrt{ 1-\zeta^2 }$               | Underdamped       |
| $\zeta=1$     | $-\zeta\omega_{n}$ (repeated)                     | Critically Damped |
| $\zeta>1$     | $-\zeta\omega_{n}\pm\omega_{n}\sqrt{ \zeta^2-1 }$ | Overdamped        |

#### Natural Frequency

The *natural frequency* $\omega_{n}$ indicates how much the system oscillates given that there is no damping.

$$
\begin{align}
w_{n}=\sqrt{ b } \\
\pm j\sqrt{ b }
\end{align}
$$

Where
- $b$ is a system pole element

#### Damping Ratio

$$
\begin{align}

\zeta&=\frac{\text{Exponential Decay Frequency}}{\omega_{n}\text{(in radians per seconds)}} \\
\zeta&=\frac{1}{2\pi}\left( \frac{\frac{1}{\omega_{n}}\text{(in seconds)}}{\text{Exponential time constant}} \right)
\end{align}
$$

## Characteristics of a General Second-Order System Transient Response

### Rise Time

The *rise time* $T_{r}$ refers to the time needed for the response to go from 10% to 90% of its steady state value.

| Damping Ratio | Normalized Rise Time |
| ------------- | -------------------- |
| 0.1           | 1.104                |
| 0.2           | 1.203                |
| 0.3           | 1.321                |
| 0.4           | 1.463                |
| 0.5           | 1.638                |
| 0.6           | 1.854                |
| 0.7           | 2.126                |
| 0.8           | 2.467                |
| 0.9           | 2.883                |

$$
T_{r}=\frac{\text{Normalized Rise Time}}{\omega_{n}}
$$

### Peak Time

The *peak time* $T_{p}$ refers to the length in time for the waveform to either reach the first or the maximum peak.

$$
T_{p} = \frac{\pi}{\omega_{n}\sqrt{ 1-\zeta^2 }}
$$

### Percent Overshoot

The *percent overshoot* $\%OS$ measures how much the waveform go beyond the steady state (expressed as a percentage of the steady state). It could also refer to the peak time’s final value.

$$
\displaystyle \%OS=e^{-(\zeta \pi/\sqrt{ 1-\zeta^2 })}\times100\%
$$

### Settling Time

The *settling time* $T_{s}$ refers to the time it takes for the response to reach and settle to 2% of its steady state value.

$$
T_{s}=\frac{-\ln(0.02\sqrt{ 1-\zeta^2 })}{\zeta\omega_{n}}
$$

It can be approximated using the formula

$$
T_{s}=\frac{4}{\zeta\omega_{n}}
$$
