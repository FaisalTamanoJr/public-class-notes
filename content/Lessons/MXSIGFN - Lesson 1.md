---
title: Differential Amplifiers
draft: false
tags:
  - MXSIGFN
date: 2025-05-10, 12:07
---
## Sources

1. Differential Amplifiers (Lecture Slides)

## Introduction

[[Differential amplifiers]] are used often to amplify voltage whereby the **difference of two inputs are obtained to amplify the signals**. In contrast to single-ended amplifiers, which amplifies both signal and noise, differential amplifiers only amplify the desired signal while **eliminating the noise**.

### Advantages

1. Besides AC, It can also provide amplification for DC signals.
2. The *symmetrical* design and *constant current source* of differential amplifiers rectifies the effects of thermal drift.[^1]
3. They do not amplify noise.

### Basic Bipolar Differential Amplifier

Characteristics of a basic bipolar differential amplifier:

- Voltage inputs are applied to the **bases**.
- Voltage outputs are extracted across the **collectors**.
- The two transistors are **biased in the forward-active region**—the base-emitter junction is forward biased while the collector-base junction is reversed biased.[^2]
- It commonly uses dual supplies which provides direct coupling and eliminates the need for capacitor coupling.[^3]

### Basic CMOS Differential Amplifier

It has a similar configuration as the bipolar differential amplifier but it has 3 key differences:

- It has a different notation.
- Voltage inputs are applied to the **gates**.
- Voltage outputs are extracted across the **drains**.

### Differential Amplifier Operations

There are three differential amplifier operational modes:

1. **Single ended:** One input receives a signal, whereas the other one is grounded. For this reason, it only has half the gain of the differential circuit.
2. **Double ended or differential input:** The two inputs receive signals which are opposite in polarity, allowing the amplifier to respond to their *difference* and thereby canceling out the noise common between them.
3. **Common mode:** The two inputs share the same polarity, amplitude, and frequency signals. Three sources of common mode signals include radiated energy on input lines, radiated energy on adjacent lines, and a 60 Hz hum.[^4]

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


> [!TIP]- 
> $V_{T}$ = thermal voltage, 26 mV
> $I_{s}$ = reverse-bias saturation $10^{-15}$ to $10^{-12}$ A


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

$$V_{o} \cong -I_{EE}R_{c}=-V_{sat}$$

#### Case 2: V1-V2 >> -100 mV

$I_{E_{1}} \approx 0$, $Q_{1}$ is cut-off

$I_{E_{2}} \approx I_{EE}$, $Q_{2}$ saturates

Output is **positive**

$$V_{o} \cong -I_{EE}R_{c}=V_{sat}$$

#### Case 3: V1=V2

$$
\begin{align}
I_{E_{1}}=\frac{I_{EE}}{2}&& \text{and} && I_{E_{2}} = \frac{I_{EE}}{2}
\end{align}
$$

$$V_{o}=0$$


> [!INFO] 
> The differential mode input $v_{d}$ **should have a small value** for the bipolar differential amplifier to operate properly in the linear region. Otherwise, one transistor will dominate and it will function less like an amplifier and more like a switch.

### Differential Gain

The current passing through $R_{E}$ ($I_{EE}$) is constant when $V_{1}$ and $V_{2}$ are equal but opposite in polarities.[^6] In other words

$$
\begin{align}
I_{E_{1}} = \frac{I_{EE}}{2}+\Delta I \\ 
I_{E_{2}} = \frac{I_{EE}}{2}-\Delta I
\end{align}
$$

This implies that the voltage across $R_{E}$ is constant and is a DC source; therefore, it is ignored in AC analysis.

In a transistor small signal equivalent circuit

$$
\begin{align}
r_{\pi} = \beta r_{e} && r_{e}=\frac{26mV}{I_{E}}
\end{align}
$$


> [!NOTE] 
> The symmetry of the transistors $Q_{1}$ and $Q_{2}$ entails that **half-circuit analysis is enough** for the AC analysis.

Formula for the differential gain:

$$A_{d}=\dfrac{V_{o}}{V_{i}}$$


> [!INFO] Table for Finding the Differential Gain Depending on the case.[^7]
> 
> | Case                                      | Formula                                                                                     | Remarks                                                                                                     |
> | ----------------------------------------- | ------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
> | Single-ended output                       | $A_{d_{n}}=\dfrac{V_{o_{n}}}{V_{d}}=-\dfrac{R_{c}}{2r_{e}}=-\dfrac{gmR_{c}}{2}$             | - If $n=1$, the output is **negative** because it is out of phase<br>- If $n=2$, the output is **positive** |
> | Double-ended output                       | $A_{d}=\dfrac{V_{o}}{V_{d}}=\dfrac{V_{o_{1}}-V_{o_{2}}}{V_{d}}=-\dfrac{R_{c}}{r_{e}}=-gmRc$ |                                                                                                             |
> | Double ended output with $r_{o}$ included | $A_{d}=\dfrac{R_{c} //r_{o}}{r_{e}}=-gm(R_{c} // r_{o})$                                    |                                                                                                             |
> 

### Common Mode Gain

- The common mode signal $V_{cm}$ is the result of having the voltage inputs $V_{1}$ and $V_{2}$ have **the same amplitude, frequency signal, and polarity**. For this reason, the two transistors are **virtually in parallel**.
- When a current change occurs on one of the transistors, the same current change will be experienced by the other transistor, and, as such, will give rise to a **small variation in the voltage** across $R_{E}$.
- Because of the small voltage variation, $R_{E}$ **remains in the small signal equivalent**.
- **Half circuit analysis only applies when $R_{E}$ is split**. This is done by getting the parallel equivalent $2R_{E}$.

| Variable                       | Formulas                                                                 |
| ------------------------------ | ------------------------------------------------------------------------ |
| Output of the first transistor | $V_{o_{1}}=\beta i_{b} R_{c}$                                            |
| Common mode signal input       | $V_{cm}=i_{b}r_{\pi}+(\beta+1)i_{b}2R_{E}$                               |
| Common mode gain               | $A_{C}=\dfrac{-g_{m}R_{C}}{1+2_{g_{m}}R_{E}}\cong-\dfrac{R_{C}}{2R_{E}}$ |

> [!NOTE]-
> $r_{\pi}=\beta r_{e}$

### Input Resistance

Differential Mode 

$$
\begin{align}
R_{id} &= r_{\pi} &&\text{single-ended} \\
R_{id} &= 2r_{\pi} &&\text{double-ended}
\end{align}
$$

Common Mode

$$
R_{ic} = 2\beta R_{E}
$$

### Output Resistance

The early voltage and the bias current impact the output resistance, thus,

$$
r_{o} = \dfrac{V_{A}}{I_{E}}
$$

### Differential Amplifier with Both Differential and Common Mode

The output voltage should **include the effects of both the differential input and common mode input** because the actual input can contain common mode signals.


> [!TIP]- Recall
> $V_{d} = V_{1}-V_{2}$
>
> $V_{cm} = (V_{1}+V_{2})/2$


$$
\begin{align}
V_{1}=V_{cm}+\frac{V_{d}}{2} && ; &&V_{2}=V_{cm}-\frac{V_{d}}{2}
\end{align}
$$
$$
V_{o} = A_{d}V_{d} + A_{cm} V_{cm}
$$

### Common Mode Rejection Ratio

The Common Mode Rejection Ratio (**CMRR**) indicates how well a differential amplifier can reject signals that are common to the two inputs. It can be obtained using the ratio of the differential gain to the common mode gain:

$$
CMRR = \dfrac{-\frac{g_{m}R_{c}}{2}}{-\frac{R_{c}}{2R_{E}}}=g_{m}R_{E}
$$


> [!INFO] Improving CMRR
> - Increasing $I_{E}$
> 	- **ISSUE:** IC fabrication would not be possible due to the enormous size of the transistor
> - Increasing $R_{E}$
> 	- **ISSUE:** $I_{E}$ will decrease, hence $g_{m}$ will also decrease. Although a greater power supply can solve this problem, its portability will be negatively affected.
> - Utilizing a constant current source with high resistance (e.g., current sources like Widlar, Wilson, and Cascode.)

### Simple Current Source

Base-emitter loop:

$$V_{BE_{1}}-V_{BE_{2}}=0$$

> [!TIP]- Recall
> $V_{BE}=V_{T}\ln\dfrac{I_{E}}{I_{s}}$

Substituting to the loop,

$$
V_{T_{1}}\ln\dfrac{I_{E_{1}}}{I_{s_{1}}} - V_{T_{2}}\ln\dfrac{I_{E_{2}}}{I_{s_{2}}} = 0
$$

Because the two transistors ($Q_{1}$ and $Q_{2}$) are identical,

$$
I_{E_{1}} = I_{E_{2}}
$$


> [!TIP]- Recall
> $I_{E}=(\beta + 1)I_{B}$
> $I_{B}=\dfrac{I_{E}}{\beta + 1}$
> $I_{REF}=I_{c_{1}}+I_{B_{1}}+I_{B_{2}} = \dfrac{\beta + 2}{\beta + 1}I_{E}$

Output current is

$$
I_{out} = \frac{\beta}{\beta + 2} I_{REF}
$$

### Widlar Current Source

Base-emitter loop:

> [!TIP]- RECALL 
> $V_{BE}=V_{T}\ln\dfrac{I_{E}}{I_{s}}$

$$V_{BE_{1}}-V_{BE_{2}}-I_{E_{2}}R_{2}=0$$
Therefore,

$$
V_{T}\ln\frac{I_{E_{1}}}{I_{E_{2}}}-I_{E_{2}}R_{2}=0
$$

The effective output resistance is

$R_{TH}=R_{E}=\dfrac{v_{th}}{i_{th}}$

The effective emitter resistance is

$$
R_{E}=r_{o}\left(1+\dfrac{I_{c_{2}}R_{2}}{V_{T}}\right)
$$

$R_{1}$, which is used to get $I_{REF}$, is equivalent to

$$
R_{1}=\frac{V_{CC}+V_{EE}-V_{BE_{1}}}{I_{REF}}
$$

### Wilson Current Source

The *Wilson current source* is valuable due to its uses in **getting a high output resistance**. Moreover, its not very sensitive towards base currents. The **output collector voltage also changes much less** when the bias current $I_{o}$ is changed, especially compared to a two-transistor current source.

It has an effective emitter resistance equivalent to

$$
R_{E} = \dfrac{\beta r_{o}}{2} = \dfrac{\beta V_{A}}{2I_{C_{2}}}
$$

### Current Mirror

- The change in the emitter area makes the currents $I_{c_{2}}$, $I_{c_{3}}$, and $I_{c_{4}}$ multiples of $I_{c_{1}}$

The transistor's saturation current is proportional to its emitter area $A_{E}$, therefore it can be obtained using the following formulae:

$$
\begin{align}
I_{s} &= I_{so}\dfrac{A}{A_{E}} \\
A &= 1xA_{E} && I_{s} = I_{so} \\
I_{C_{2}} &= n_{1}I_{REF} && n_{1} = \dfrac{A_{E_{2}}}{A_{E_{1}}} \\
I_{C_{3}} &= n_{2}I_{REF} && n_{2} = \dfrac{A_{E_{3}}}{A_{E_{1}}} \\
\end{align}
$$

### Differential Amplifier with Current Source

The differential gain is equal to

$$
A_{d} = -g_{m}R_{c}
$$

The common mode gain is equal to

$$
A_{c} \cong - \dfrac{R_{C}}{2R_{E}}
$$

Where

$R_{E}=r_{o}\left(1+\dfrac{I_{c_{2}}R_{2}}{V_{T}}\right)$

### Differential Amplifier with Active Loads

$Q_{1}$ and $Q_{2}$ make up the differential amplifier pare, whereas $Q_{3}$ and $Q_{4}$ comprise the constant current source. On the other hand, $Q_{5}$, $Q_{6}$, and $Q_{7}$ form the active loads
### Current Reference

$$
\begin{align}
I_{C_{1}} = \frac{V_{EE}-1.4V}{R_{1}} && I_{C_{2}} \cong \frac{V_{T}}{R_{2}}\ln \frac{V_{EE}-1.4V}{I_{S_{1}}R_{1}}
\end{align}
$$

The output current is only logarithmically  contingent on the supply voltage $V_{EE}$'s changes.

## Basic MOS Differential Amplifier


[^1]: Thermal drift refers to the changes in the device behavior as a result of the variations in temperature.

[^2]: Being biased in the forward-active region allows the transistor to amplify the signal. Unwanted current flow is attenuated by preventing the current from flowing between the collector and base. Consequently, current becomes more concentrated between the base and the emitter.

[^3]: Direct coupling allows the transistor to amplify the output while maintaining a balanced DC bias voltage. Dual supplies (also known as *split supplies*) have an arrangement where two power supplies are in series, with a ground connected between them.

[^4]: Radiated energy refers to a wireless energy source. 60 Hz hum is a ripple voltage originating from a DC signal.

[^5]: The quiescent point provides the initial conditions needed to find the steady-state DC voltages and currents.

[^6]: $I_{EE} = I_{E_{1}} + I_{E_{2}}$

[^7]: $n$ refers to the particular transistor. For example, the first half transistor $Q_{1}$ will have $n=1$, while the other half $Q_{2}$ will have $n=2$.

