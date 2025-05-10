---
title: Differential Amplifiers
draft: false
tags:
  - MXSIGFN
date: 2025-05-10, 12:07
---
> [!WARNING] 
> The content here is still **INCOMPLETE**

## Sources

1. Differential Amplifiers (Lecture Slides)

## Introduction

[[Differential amplifiers]] are used often to amplify voltage whereby the **difference of two inputs are obtained to amplify the signals**. In contrast to single-ended amplifiers, which amplifies both signal and noise, differential amplifiers only amplify the desired signal while **eliminating the noise**.

### Advantages

1. They can filter out DC signals when AC coupling is applied.[^1]
2. The *symmetrical* design and *constant current source* of differential amplifiers rectifies the effects of thermal drift.[^2]
3. They do not amplify noise.

### Basic Bipolar Differential Amplifier

Characteristics of a basic bipolar differential amplifier:

- Voltage inputs are applied to the **bases**.
- Voltage outputs are extracted across the **collectors**.
- The two transistors are **biased in the forward-active region**—the base-emitter junction is forward biased while the collector-base junction is reversed biased.[^3]
- It commonly uses dual supplies which provides direct coupling and eliminates the need for capacitor coupling.[^4]

### Basic CMOS Differential Amplifier

It has a similar configuration as the bipolar differential amplifier but it has 3 key differences:

- It has a different notation.
- Voltage inputs are applied to the **gates**.
- Voltage outputs are extracted across the **drains**.

### Differential Amplifier Operations

There are three differential amplifier operational modes:

1. **Single ended:** One input receives a signal, whereas the other one is grounded. For this reason, it only has half the gain of the differential circuit.
2. **Double ended or differential input:** The two inputs receive signals which are opposite in polarity, allowing the amplifier to respond to their *difference* and thereby canceling out the noise common between them.
3. **Common mode:** The two inputs share the same polarity, amplitude, and frequency signals. Three sources of common mode signals include radiated energy on input lines, radiated energy on adjacent lines, and a 60 Hz hum.

## Bipolar Differential Amplifier Analysis

Analysis can be performed in terms of DC or AC.

- DC analysis is focused on **determining the quiescent or bias point**.[^5] 
- AC analysis revolves around **finding the differential gain in differential mode** and **finding the common mode gain in common mode**.

| Differential Mode Input | Common Mode Input               |
| ----------------------- | ------------------------------- |
| $v_{d}=V_{1}-V_{2}$     | $v_{cm}=\dfrac{V_{1}+V_{2}}{2}$ |

### DC Analysis

> [!SUMMARY]
> 
> |                           | Output             | Remarks                                |
> | ------------------------- | ------------------ | -------------------------------------- |
> | Case 1: $V_{1} > > V_{2}$ | $V_{o} = -V_{sat}$ | $Q_{1}$ is the **inverting** input     |
> | Case 2: $V_{1} < < V_{2}$ | $V_{o} = V_{sat}$  | $Q_{2}$ is the **non-inverting** input |
> | Case 3: $V_{1} = V_{2}$   | $V_{o}=0$          | Common mode condition                  |
>

Base-emitter loop

$$
\begin{align}
V_{EE} - V_{BE_{1}}-I_{EE}R_{E}=0 && \text{and} && 
V_{EE} - V_{BE_{2}}-I_{EE}R_{E}=0
\end{align}
$$

When $V_{1}$ and $V_{2}$ are applied to the inputs, we get the loop $V_{1}-V_{BE_{1}}+V_{BE_{2}}-V_{2}=0$ and allows us to derive the following equations:

$$
\begin{align}
I_{E_{1}} = \frac{I_{EE}}{1+e^{-(\frac{V_{1}-V_{2}}{V_{T}})}} && \text{and} && I_{E_{2}} = \frac{I_{EE}}{1+e^{\frac{V_{1}-V_{2}}{V_{T}}}}
\end{align}
$$

$V_{o}=(I_{c_{2}}-I_{c_{1}})R_{c}$

#### Case 1: V1-V2 >> 100 mV

$I_{E_{1}} \approx I_{EE}$, $Q_{1}$ saturates
$I_{E_{2}} \approx 0$, $Q_{2}$ is cut-off

Output is **negative**

$V_{o} \cong -I_{EE}R_{c}=-V_{sat}$

#### Case 2: V1-V2 >> -100 mV

$I_{E_{1}} \approx 0$, $Q_{1}$ is cut-off
$I_{E_{2}} \approx I_{EE}$, $Q_{2}$ saturates

Output is **positive**

$V_{o} \cong -I_{EE}R_{c}=V_{sat}$

#### Case 3: V1=V2

$$
\begin{align}
I_{E_{1}}=\frac{I_{EE}}{2}&& \text{and} && I_{E_{2}} = \frac{I_{EE}}{2}
\end{align}
$$

$V_{o}=0$ 


> [!INFO] 
> The differential mode input $v_{d}$ **should have a small value** for the bipolar differential amplifier to operate properly in the linear region. Otherwise, one transistor will dominate and it will function less like an amplifier and more like a switch.

### Differential Gain

### Common Mode Gain

### Input Resistance

### Output Resistance

### Differential Amplifier with Both Differential and Common Mode

### Common Mode Rejection Ratio (CMRR)

### Simple Current Source

### Widlar Current Source

### Wilson Current Source

### Current Mirror

### Differential Amplifier with Current Source

### Differential Amplifier with Active Loads

### Current Reference

## Basic MOS Differential Amplifier

[^1]: AC coupling is a technique wherein capacitors in series are utilized for blocking DC signals while allowing AC signals to pass through.

[^2]: Thermal drift refers to the changes in the device behavior as a result of the variations in temperature.

[^3]: Being biased in the forward-active region allows the transistor to amplify the signal. Unwanted current flow is attenuated by preventing the current from flowing between the collector and base. Consequently, current becomes more concentrated between the base and the emitter.

[^4]: Direct coupling allows the transistor to amplify the output while maintaining a balanced DC bias voltage.

[^5]: The quiescent point provides the initial conditions needed to find the steady-state DC voltages and currents.
