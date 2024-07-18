---
draft: false
tags: [NUMMETS]
title: Iterative Non-Bracketing Methods
---

## Iterative Non-bracketing Methods

### Newton-Raphson Method

#### Newton-Raphson Method

$$
x_{i+1}=x_{i}-{\frac{f(x_{i})}{f^{\prime}(x_{i})}}
$$

#### Secant Method

$$
x_{i+1}=x_{i}-{\frac{f(x_{i})(x_{i-1}-x_{i})}{f(x_{i-1})-f(x_{i})}}
$$

#### Modified-secant Method

$$
x_{i+1}=x_{i}-{\frac{\delta x_{i}f(x_{i})}{f(x_{i}+\delta x_{i})-f(x_{i})}}
$$

### Multiple Roots

#### Multiple Roots

$$
x_{i+1}=x_{i}-{\frac{f(x_{i})f^{\prime}(x_{i})}{[f^{\prime}(x_{i})]^{2}-f(x_{i})f^{\prime\prime}(x_{i})}}
$$

#### Newton-Raphson for Systems of Nonlinear Equations

$$
\text{Two Equation Version of the Newton-Raphson Method}
$$

$$
\begin{align}\displaystyle{\mathrm{x}}_{i+1}=\mathrm{x}_{i}-{\frac{u_{i}{\frac{\partial v_{i}}{\partial y}}-v_{i}{\frac{\partial u_{i}}{\partial y}}}{{\frac{\partial u_{i}}{\partial x}}{\frac{\partial v_{i}}{\partial y}}-{\frac{\partial u_{i}}{\partial y}}{\frac{\partial v_{i}}{\partial x}}}}\\\displaystyle{\mathrm{y}}_{i+1}=\mathrm{y}_{i}-{\frac{v_{i}{\frac{\partial u_{i}}{\partial x}}-u_{i}{\frac{\partial v_{i}}{\partial x}}}{{\frac{\partial u_{i}}{\partial x}}{\frac{\partial v_{i}}{\partial y}}-{\frac{\partial u_{i}}{\partial y}}{\frac{\partial v_{i}}{\partial x}}}}   \\\end{align}
$$

### Iterative Polynomial Function Techniques

#### Müller’s Method

To find the root, we apply the formula:

$$
x_{3}=x_{2}+{\frac{-2c}{b\pm{\sqrt{b^{2}-4a c}}}}
$$

> [!NOTE]
> - Before using this formula, take the value of the discriminant $\sqrt{ b^2-4ac }$ to determine whether to use $+$ or $-$
> 	- If $\left|b+\sqrt{ b^2-4ac }\right| > \left|b-\sqrt{ b^2-4ac }\right|$, then use a **positive** sign
> 	- If $\left|b+\sqrt{ b^2-4ac }\right| < \left|b-\sqrt{ b^2-4ac }\right|$, then use a **negative** sign

Hence, the final error is

$$
\ \epsilon_{a}=\left|{\frac{x_{3}-\,x_{2}}{x_{3}}}\right|100\%
$$

To solve for $a$, $b$, and $c$:

$$
\begin{array}{c}{{a={\frac{\delta_{1}-\delta_{0}}{h_{1}+h_{0}}}}}\\ {{b=a h_{1}+\delta_{1}}}\\c=f(x_{2})\end{array}
$$

To solve for $\delta_{1}$, $\delta_{0}$, $h_{1}$, and $h_{0}$:

$$
\begin{array}{r l}{h_{0}=x_{1}-x_{0}}&&h_{1}=x_{2}-x_{1}\\ {\delta_{0}={\frac{f(x_{1})-f(x_{0})}{x_{1}-x_{0}}}\,}&{{}}&{{}\delta_{1}={\frac{f(x_{2})-f(x_{1})}{x_{2}-x_{1}}}}\end{array}
$$

To update the initial estimates for the next iteration:

 $$
\begin{align}x_{0_{\text{new}}}=x_{{1}_{\text{old}}} \\ x_{1_{\text{new}}}=x_{{2}_{\text{old}}} \\ x_{2_{\text{new}}}=x_{{3}_{\text{old}}}\end{align}
$$

#### Bairstow’s Method

> [!example] Steps:
> 1. Guess a value for the root $x=t$
> 2. Divide the polynomial by the factor $x-t$
> 3. Determine whether there is a remainder
> 	- If there is no remainder, then the root is equal to $t$
> 	- If there is a remainder, then adjust the guess and repeat step 1-3
> 1. Repeat the entire procedure to find another root

Given a general polynomial:

$$
fn(x)=a_{0}+a_{1}x+a_{2}x^2+\dots+a_{n}x^n
$$

To solve the value of the coefficients after dividing the given polynomial with the quadratic factor $x^2-rx-s$, use the recurrence relationship:

$$
\begin{align}b_{n}&=a_{n} \\ b_{n-1}&=a_{n-1}+rb_{n} \\ b_{i}&=a_{i}+rb_{i+1}+sb_{i+2} && \text{for } i=n-2 \text{ to } 0\end{align}
$$

$$
\begin{align}c_{n}&=b_{n} \\ c_{n-1}&=b_{n-1}+rc_{n} \\ c_{i}&=b_{i}+rc_{i+1}+sc_{i+2} && \text{for } i=n-2 \text{ to } 1\end{align}
$$

To solve for the initial guesses of $r$ and $s$ (use the systems of equations function in your scientific calculator by clicking Mode→5→1):

$$
\begin{align}c_{2}\Delta r+c_{3}\Delta s=-b_{1}\\c_{1}\Delta r+c_{2}\Delta s=-b_{0}\end{align}
$$

To find the approximate error in $r$ and $s$:

$$
\begin{align}|\epsilon_{a,r}|=\left|\frac{\Delta r}{r}\right|100\% \\ |\epsilon_{a,s}|=\left|\frac{\Delta s}{s}\right|100\%\end{align}
$$

To solve for the value of the roots ($|\epsilon_{a,r}|$ and $|\epsilon _{a,s}|$ must be below $\epsilon_{s}$):

$$
x={\frac{r\,\pm\,{\sqrt{r^{2}+4s}}}{2}}
$$

> [!EXAMPLE] Three possibilities after doing the steps above:
> 1. **Quotient is a third order polynomial or greater** - apply Bairstow’s method to the quotient and solve for new values of $r$ and $s$. Use the previous $r$ and $s$ as starting guesses.
> 2. **Quotient is a quadratic** - evaluate the remaining two roots using $x={\frac{r\,\pm\,{\sqrt{r^{2}+4s}}}{2}}$
> 3. **Quotient is a first-order polynomial** - evaluate the remaining root using $x=-\frac{s}{r}$
