---
draft: false
tags: [FEECONS]
title: Time Response
date: 2024-11-02, 19:19
---

## Sources

1. Class Lecture

## Terminologies

- *Transient response* is the system’s response after it changes from a steady state.
- *Output response* refers to the sum of the natural and forced response.
	- The *forced response* comes from the input after partial fraction expansion and inverse Laplace transform has been performed.
	- The *natural response* comes from the resulting partial fraction expansion and inverse Laplace transform performed on the transfer function, excluding the one from the input.
- *Zeros* are located at the numerator of a transfer function, and are represented by $0$.
- *Poles* are located at the denominator of a transfer function, and are represented by $X$.

## The S Plane

- The $y$ axis represents $J\omega$, while the $x$ axis represents the $\phi$

## Finding the Evolution of the System Response

Steps:

1. Perform *partial fraction expansion*.
2. Solve for the inverse Laplace transform.

## First Order Systems

If the input is a unit step, the general form of the first order system is

$$
C(s) = R(s)G(s) = \frac{a}{s(s+a)}
$$

where

- $C(s)$ is the output
- $R(s)$ is the input
- $G(s)$ is the transfer function

Therefore

$$
c(t) = \text{forced response } + \text{natural response} = 1-e^{-at}
$$

(through derivations)

### Characteristics of the Transient Response

#### Time Constant

When $\displaystyle t=\frac{1}{a}$

$$
\begin{align}
e^{-at}|_{t=\frac{1}{a}} &= e^{-1} &= 0.37 \\
c(t) &= 1-0.37 &=0.63
\end{align}
$$

As a result, $\displaystyle \frac{1}{a}$ is the *time constant* indicating the time needed for $\displaystyle e^{-at}$ to decay to $37\%$ of its initial value.

#### Rise Time

The *rise time* $T_{r}$ refers to the time needed for the response to go from 10% to 90% of its steady state value.

$\displaystyle T_{r}=\frac{2.2}{a}$

#### Settling Time

The *settling time* $T_{s}$ refers to the time it takes for the response to reach and settle to 2% of its steady state value.

$$
T_{s} = \frac{4}{a}
$$

## Second Order Systems

If the input is a unit step, the general form of the second order system is

$$
G(s) = \frac{b}{s^2+as+b}
$$

> [!TIP]
> You can easily find the roots of a second order system using a scientific calculator by clicking mode -> EQN -> $aX^2+bX+C=0$

### Types of Responses

#### Overdamped Response

| Key    | Value                                               |
| ------ | --------------------------------------------------- |
| Poles  | Two real at $-\sigma_{1}$ and $-\sigma_{2}$         |
| $c(t)$ | $K_{1}+K_{2}e^{-\sigma_{1}t}+K_{3}e^{-\sigma_{2}t}$ |

#### Underdamped Response

| Key    | Value                                               |
| ------ | --------------------------------------------------- |
| Poles  | Two complex at $-\sigma_{d}\pm j\omega_{1}$         |
| $c(t)$ | $K_{1}+K_{4}e^{-\sigma_{d}}\cos(\omega_{1} t+\phi)$ |

> [!NOTE]
>
> - $\phi=\tan^{-1} \frac{K_{3}}{K_{2}}$
> - $K_{4}=\sqrt{ K_{2}^2+K_{3}^2 }$

#### Undamped Response

| Key    | Value                                |
| ------ | ------------------------------------ |
| Poles  | Two imaginary at $at\pm j\omega_{1}$ |
| $c(t)$ | $K_{1}+K_{4}\cos(3t+\phi)$           |

#### Critically Damped Response

| Key    | Value                                                |
| ------ | ---------------------------------------------------- |
| Poles  | Two real at $-\sigma_{1}$                            |
| $c(t)$ | $K_{1}+K_{2}e^{-\sigma_{1}t}+K_{3}te^{-\sigma_{2}t}$ |
