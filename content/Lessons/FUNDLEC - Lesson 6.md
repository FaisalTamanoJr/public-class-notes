---
title: Bipolar Junction Transistor Part 1
draft: false
tags: [FUNDLEC]
date: 2024-11-24, 16:30
---

## Sources

1. Bipolar Junction Transistor (BJT) (Lecture Slides)
2. Class Lecture

## Introduction

> [!INFO] Types of Transistors
> 1. Junction Field Effect Transistor (JFET)
> 	- **Voltage** driven devices
> 1. Bipolar Junction Transistor (BJT)
> 	- A **current** triggering device

A *bipolar junction transistor* is a three-terminal electronic device composed of either the following:

1. two P-type materials and one N-type material.
	- It has a **negative base** activation because of the P at the center.
	- In the electronic symbol, the arrow is pointing **towards the base**.
2. or two N-type materials and one P-type material;
	- It has a **positive base** activation because of the P at the center.
	- In the electronic symbol, the arrow is pointing **away from the base**.

![BJT illustration](https://www.mepits.com/kcfinder/upload/images/Bipolar-Junction-Transistor.png)

- The **input** is located at the base activation. Conversely, the **output** is located at the collector and emitter.

## Operation

Because a BJT is a three-terminal device, there are three ways of biasing it.

| Base-Emitter Junction | Base-Collector Junction | Region of Operation |
| --------------------- | ----------------------- | ------------------- |
| forward bias          | reverse bias            | Active region       |
| reverse bias          | reverse bias            | Cut-off region      |
| forward bias          | forward bias            | Saturation region   |

- The base can either be paired with the emitter or the collector because it is at the neutral side.
- There is **no current** at the cut-off region.

> [!TIP]- Forward Bias and Reverse Bias
> Forward bias implies that there is a high current. In contrast, reverse bias implies that there is a high resistance.

The *Eber’s Moll model* is used to visualize the behavior of a BJT transistor. It contains two diodes: a Base-Emitter PN junction representation and a Base-Collector PN junction. In addition, it also contains a dependent current source between the base and collector—a function of the current gain, $\alpha$ or $\beta$.

- $\displaystyle \alpha = \frac{I_{C}}{I_{E}}=\frac{I_{o}}{I_{i}}$
	- Used for common base design (base is at ground)
- $\displaystyle \beta=\frac{I_{C}}{I_{B}}$
	- Used for common emitter design (emitter is at ground)
- $\displaystyle \gamma=\frac{I_{E}}{I_{B}}$
	- Used for common collector design (collector is at ground)

1. PNP - both output has currents going up, while the input is leaving through the base.
2. NPN - both output has currents going down, while the input is entering through the base.

### Active Region

- base-emitter is forward biased
- base-collector is reverse biased
- Plenty of majority carriers (electrons) will diffuse around the base-emitter junction. When these electrons go into the base region, they may leave through the base resistance to the positive terminal of $V_{BB}$, or they may flow towards the collector region (usually the latter).
- The base region is very thin.
- Few amount of current, $I_{CO}$ flow through the transistor due to the minority carriers.

### Cutoff Region

- both base-emitter junction and base-collector junction are reverse biased.
- Small amount of leakage current $I_{CO}$ resulting from a widening of the depletion region (usually neglected due to minimal impact)
- Two diodes act like open circuits (with current through them equal to 0 and max voltage across them $V_{CE(off)}$) in the Eber’s Moll model since it is reverse biased.
- $V_{CE}(off)$ = $V_{CC}$

### Saturation Region

- Both base-emitter junction and base-collector junction are forward biased.
- Net voltage drop present between the collector and emitter $V_{CE}(sat)$ would be equal to 0 since base-emitter voltage $V_{BE}$ and base-collector voltage $V_{CE}$ are opposing and are equal.
- Transistor acts like a short circuit. Its maximum current $_{I_{C(sat)}}$ flows through the transistor.

## BJT Output Characteristic Curve

- Active region is between the saturation region and the cut-off region.
- The saturation region has the maximum amount of collector current $I_{C}$ but has no collector-emitter voltage $V_{CE}$.
- The cut-off region has the minimum amount of collector current $I_{C}$ but has the maximum collector-emitter voltage $V_{CE}$.
- The best and most stable value is located at the Q-point or the quiescent point.

## Basic Transistor Formulas

- $I_{E}=I_{C}+I_{B}$
- $I_{C}=I_{CMAJ}+I_{CO}$
- $\alpha_{AC}=\frac{\Delta I_{C}}{\Delta I_{E}}$
- $\alpha_{DC}=\frac{I_{C}}{I_{E}}$
- $I_{C} = \alpha I_{E} + I_{CO}$
- $I_{B}=\frac{(1-\alpha)}{\alpha}I_{C}$
- $I_{B}=(1-\alpha)I_{E}$
- $\beta=\frac{I_{C}}{I_{B}}$
- $I_{C}=\beta I_{B}$
- $\alpha=\frac{\beta}{\beta+1}$
- $\beta=\frac{\alpha}{1-\alpha}$

## BJT Amplifier Configuration

To identify the configuration (whether it is Common Base, Common Emitter, or Common Collector), check where the input source and output source is. The one without the voltage source indicates the common type (because of the ground).
