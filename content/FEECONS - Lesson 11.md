---
draft: false
tags: [FEECONS]
title: State Space Representation
date: 2024-11-05, 21:03
---

The *state space approach* to modeling, also known as the *time domain approach*, is a helpful way of representing systems even with **non-zero initial conditions**.

## General State-Space Representation

$$
\begin{align}
\dot{x} = Ax+Bu \\
y = Cx+Du
\end{align}
$$

Assumptions:
- Time is greater than or equal to the initial time ($t\geq t_{0}$ )
- Initial conditions $x(t_{0})$

Where:

$$
\begin{align}
x &= \text{state vector} \\
\dot{x} &= \text{derivative of the state vector with respect to time }\left( \frac{dx}{dt} \right) \\
y &= \text{output vector} \\
u &= \text{input vector} \\
A &= \text{system matrix} \\
B &= \text{input matrix} \\
C &= \text{output matrix}  \\
D &= \text{feedforward matrix}
\end{align}
$$

### Steps for Finding the State Space Representation given an Electrical Network

1. Assign a label to all branch currents.
2. Determine the state variables using the derivative equations drawn from energy storing elements.
3. Take advantage of Kirchhoff’s laws to compute for the required currents and voltages. Replace the currents of non-energy storing elements using Ohm’s law.
4. Use the resulting equations from step 3 and substitute it to the equations found in step 2.
5. Use the previous values and substitute them into the $\dot{x}$, the system matrix $A$, the state vector $x$, the input matrix $B$, and the input vector $u$.
6. Write the output equations.
