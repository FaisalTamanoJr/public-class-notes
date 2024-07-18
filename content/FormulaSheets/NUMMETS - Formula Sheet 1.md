---
draft: false
tags: [NUMMETS]
title: Iterative Bracketing Methods
---

## Iterative Bracketing Methods

### Graphical Method

1. Use different values of $x$ and substitute them into the equation
2. Using the graph, roughly approximate the root of the function—the point where $f(x)=0$.

### Bisection and False-position Method

1. Choose lower $x_{l}$ and upper $x_{u}$ for the root such that the function changes signs over the interval. This can be checked by ensuring that $f(x_{l})f(x_{u})$ < 0.
2. An estimate of the root $x_{r}$ is determined by $\begin{align}\text{bisection method} &&x_{r} = \frac{x_{l}+x_{u}}{2} \\ \text{false-position method} &&x_{r}=x_{u}-{\frac{f(x_{u})(x_{l}-x_{u})}{f(x_{l})-f(x_{u})}} \end{align}$
3. Make the following evaluations to determine in which subinterval the root lies:
	1. if $f(x_{l})f(x_{r}) < 0$, the root lies in the lower subinterval. Therefore, set $x_{u} = x_{r}$ and repeat step 2.
	2. if $f(x_{l})f(x_{r}) > 0$, the root lies in the upper subinterval. Therefore, set $x_{l}=x_{r}$, and repeat step 2.
	3. If $f(x_{l})f(x_{r}) = 0$, the root equals $x_{r}$; terminate the computation.
4. Keep solving for better $x_{r}$ (root from a particular iteration) if $\epsilon_{a}>\epsilon_{s}$. The percent relative error $\epsilon_{a}$ is determined by

$$
\varepsilon_{a}=\left|{\frac{x_{r}^{n e w}-x_{r}^{o l d}}{x_{r}^{n e w}}}\right|\times100\%
$$
