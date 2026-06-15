---
draft: false
tags: [FUNDLEC]
title: Diode Applications - Clipping and Clamping Circuits
date: 2024-09-30, 22:25
---

## Sources

1. Diode Circuit Applications Part 1 (Lecture Slides)
2. Class Lecture

## Clipping Circuits

- [[clippers|Clippers]] removes a part of an input signal (either the top or bottom part)
	- The output signal retained depends on the direction of the diode: upwards and right is positive, while downwards and left is negative.
- *Clipping line* (or clipping line voltage) the marker that indicates where the signal clips off
	- It only appears in a **forward-bias condition**
	- It depends on the magnitude of the voltage where the diode is located
- We only change the polarities of the **input voltage** when we have a **reverse-bias condition**
- The output voltage is equal to the the voltage of the component (s) parallel to it.
- diode voltage is 0 when the diode is ideal (in forward bias)
- *Bias clipper* - has voltage in its output
- *Series clipper* - left or right direction
- *Parallel clipper* - up or down direction

## Clamping Circuits

- *Clamping line* is equal to the output voltage and only appears in a **forward-bias** condition
- $\tau$ is the charge up time
- The direction of the diode determines where to amplify the voltage (negative or positive side)

### Analytical Method

1. Determine which part of the input signal will make the diode forward-bias for the first time. This is when the capacitor quickly charges to the circuit’s max voltage level.
2. When the diode is in a reverse-bias, the capacitor holds unto its stored voltage and discharges for a time period of $\tau=RC$. This time constant is usually amplified ten times the input signal to ensure that the capacitor voltage remains constant when the diode is off.
3. For each condition, solve for the clamping circuit’s output waveform.
	- It should exactly match the input but with a different DC level.

## Designing of Circuits
