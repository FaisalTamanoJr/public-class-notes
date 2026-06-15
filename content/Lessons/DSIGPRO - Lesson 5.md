---
title: Direct Z Transform
draft: false
tags: [DSIGPRO]
date: 2026-06-15, 21:45
---

## Sources

1.  DirectZTransform (Lecture Slides)
2. Lecture Notes


> [!NOTE] Note
> 1. There is no Example 1.C.  I don't think sir included it.

## Example 1

### A.

> [!INFO] Problem
> $$
> x_{1}[n] = \{\underset{\uparrow}1,2,5,7,0,1\}
> $$

$$
\begin{align}

x_{1}[n] &= \delta[n] + 2 \delta[n-1] + 5 \delta[n-2] + 7\delta[n-3] + \delta[n-5]  \\ \\

X_{1}(z) &= \sum^5_{n=0}x(n)z^{-n} \\
&= x[0]z^{-0} + x[1]z^{-1} + x[2]z^{-2} + x[3]z^{-3} + x[4]z^{-4} + x[5]z^{-5}  \\
\end{align}
$$


$$
\boxed{X_{1}(z)=1 + 2z^{-1} + 5z^{-2}+ 7z^{-3} + z^{-5}}
$$

Region of Convergence (ROC): Entire z-plane
### B.


> [!INFO] Problem
> $$
> x_{2}[n] = \{1,2,\underset{\uparrow}5,7,0,1\}
> $$

$$
\boxed{X_{2}(z) = z^2 + 2z + 5 + 7z^{-1} + z^{-3}}
$$
### C.

> [!INFO] Problem
> 
> $$
> x_{3}[n] = \{\underset{\uparrow}0,0,1,2,5,7,0,1\}
> $$

$$
\boxed{X_{3}(z) = z^{-2} + 2z^{-3} + 5z^{-4} + 7z^{-5} + z^{-7}}
$$

ROC: entire z-plane except $z=0$

### E.

> [!INFO] Problem
> 
> $$
> \begin{align}
> x_{5}[n]=\delta[n-k], && k>0
> \end{align}
> $$

### F.

> [!INFO] Problem
> 
> $$
> \begin{align}
> x_{6}[n]=\delta[n+k], && k>0
> \end{align}
> $$
