---
title: Bipolar Junction Transistor Part 2
draft: false
tags: [FUNDLEC]
date: 2024-11-25, 18:44
---

## Sources

1. Bipolar Junction Transistor (BJT) Part 2 (Lecture Slides)
2. Class Lecture

## DC Analysis

### Emitter Stabilized Bias Circuit

- Stabilizes the fixed bias configuration by adding $R_{E}$: it makes the transistor’s DC currents and voltages closer even when the temperature and $\beta$ varies.
- The capacitor voltage is constant, so in DC analysis, it is treated as an open circuit to isolate the AC signals.
- Formulas
	- $I_{E}=(\beta+1)I_{B}$
- Get the outer loop formula through KVL (Counter clockwise, following the flow of the current)
- $V_{CE(SAT)}=0$ when at saturation region
- $\displaystyle I_{C}=\frac{I_{E}}{\alpha}$
- $I_{C}=0$ and $V_{CE}=V_{CC}$ when at cut-off region
- quiescent operating point midway = 1/2 of quiescent.
- 1/5 of emitter base resistance means 1/5 of emitter because the emitter was said first.

### Voltage Divider Bias Circuit

- In a **fixed bias configuration** and a **emitter stabilized configuration**, $I_{CQ}$ and $V_{CEQ}$ is dependent on $\beta$.
	- Because $\beta$ is **temperature sensitive**, a temperature increase will change $I_{CQ}$ and $V_{CEQ}$.
- A *voltage divider bias circuit* is nearly independent of $\beta$, thus solving the problems introduced by it.
	- Even if $I_{BQ}$ changes when $\beta$ changes, the operating point defined by $I_{CQ}$ and $V_{CEQ}$ remains constant as long as the appropriate parameter is utilized.

> [!TIP]
> - $I_{CQ}$ and $V_{CEQ}$ are the output current and voltage.
> - The quiescent point is the point wherein the transistor operates at its most optimal state.

Two methods of analyzing this bias circuit:

1. Exact method
2. Approximate method

Some Included Components

1. 2 base resistors ($R_{B1}$ and $R_{B2}$)
2. 1 emitter resistor
3. 1 collector resistor

> [!TIP]
> - Unlike **fixed-bias**, it has $R_{E}$
> - Unlike **emitter-stabilized**, it has $R_{B2}$

#### Exact Method of Analyzing Voltage Divider Bias Circuit

Although it does not seem obvious, the two base resistors are parallel to each other. Their combination is $R_{TH}$, while their combined voltage is $V_{TH}$.

- $\displaystyle V_{TH}=\frac{V_{CC}R_{B2}}{R_{B1}+R_{B2}}$
- $\displaystyle R_{TH}=\frac{R_{B1}R_{B2}}{R_{B1}+R_{B2}}$

Then use methods/formulas similar to the ones in the previous biases (emitter stabilized and fixed) to solve for the other values.

#### Approximate Method

In order to use this method, the following conditions must be satisfied:

1. $(\beta+1)R_{E}\geq10R_{B2}$
2. $\beta R_{E}\geq10R_{B2}$

When this conditions are satisfied, it implies that the $I_{B}$ is almost 0; therefore, we can replace it with an **open circuit**. Hence $I_{E} \approx I_{C}$

### Voltage Feedback Bias Circuit

The additional node will result in two currents flowing through it (e.g., $I_{C}$ and $I_{C'}$).

- $I_{C'}=I_{C}+I_{B}$
- $I_{C'}=I_{E}$
