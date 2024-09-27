---
draft: false
tags: [FUNDLEC]
title: Diode Circuit Analysis
date: 2024-09-27, 20:42
---

## Sources

1. Diode Circuit Analysis (Lecture Slides)
2. Class Lecture

## Graphical Solution

STEPS

1. Get the [[Kirchhoff’s Voltage Law|KVL]] equation
	1. For it to be forward-biased, the source and diode voltage should have their similar polarities be connected to one another (e.g., positive side of source voltage is connected with positive side of diode).
2. Get the **status** based on the $V_{T}$
	1. Increasing current when **forward-biased**. The circuit is forward-biased when $V_{S} > V_{T}$
		1. Turn on voltage is 0.7V for silicon
		2. Turn on voltage is 0.3V for germanium
	2. Decreasing current when **reversed-biased**. The circuit is reversed-biased when $V_{S}<V_{T}$
		1. Turn on voltage is 0.7V for silicon
		2. Turn on voltage is 0.3V for germanium
3. Load Line Analysis
	1. Get the $x$ and $y$ intercept by substituting 0s to the solved KVL equations
		- The $x$ is equal to the $V_{D}$
		- The $y$ is equal to the $I_{D}$
4. Get the quiescent point $Q-pt$ because it is the best operating condition of a diode
	1. $V_{DQ}$
	2. $I_{DQ}$

> [!TIP] Tip
> The quiescent point will be at the intersection between the load line—which you can find using the $x$ and $y$ intercepts—and the characteristic curve

## Analytical

STEPS

1. Get the **status** based on the $V_{T}$
	1. Increasing current when **forward-biased**. The circuit is forward-biased when $V_{S} > V_{T}$
		1. Turn on voltage is 0.7V for silicon
		2. Turn on voltage is 0.3V for germanium
	2. Decreasing current when **reversed-biased**. The circuit is reversed-biased when $V_{S}<V_{T}$
		1. Turn on voltage is 0.7V for silicon
		2. Turn on voltage is 0.3V for germanium
2. Modeling, by performing KVL
	- Ideal
		- Does not have Si or GE
	- Complete Piecewise Model
		- Has Si and Ge and Rf/Rr
		- When redrawing, draw the Si or Ge as a voltage source first, then the $Rf$ as a resistor
	- Approximate Piecewise Model
		- Has Si and Ge but no Rf/Rr
		- Open switch when reverse-biased

> [!TIP] Tips
> - The ideal diode in KVL is equal to 0 when it is forward-biased (it is short circuited)
> - If you have two sources, find their KVL (of only sources) to check if its status
> - A circuit with diodes are not limited to one bias conditions; multiple diodes can have different statuses.
> - When there are two differing diodes (i.e., one is silicon while the other is germanium) parallel to the output voltage, the one with a lower voltage is forward-biased while the one with a higher voltage is reverse-biased because the lower voltage activates first (according to the [[FUNDLEC - Lesson 3|characteristic curve]]).
> 	- As a result, we treat the higher voltage like it is not there (open switch), only the diode with a lower voltage. Furthermore, we will use the lower voltage as the parallel when computing for the output voltage.
> - To limit the computation, find if it is reverse or forward biased because after you find its condition, you will remove the reverse-biased diodes
