---
title: Line Coding
draft: false
tags: [DIGDACM]
date: 2025-06-15, 17:59
---

## Sources

1. Lecture Slides
2. Class Lecture

## What is Line Coding

- Also known as **Pulse Modulation**
- The conversion of binary data to digital signals for baseband transmission purposes.[^1]
- Each pulse unit is referred to as a **symbol**[^2]
- Common pulse modulation techniques:
	- NRZ-L
	- NRZI
	- Bipolar-AMI
	- Pseudoternary
	- Manchester
	- Differential Manchester
- Categories
	- Unipolar, polar or bipolar
		- **Unipolar:** zero, positive, or negative
		- **Polar:** two polarities―positive and negative
		- **Bipolar:** two polarities and a zero
	- NRZ, RZ, Phase encoded or Multilevel binary
		- **NRZ:** two levels
		- **RZ:** three levels
		- **Phase-encoded:** uses phase inversion
		- **Multilevel Binary**

## Line Coding Properties

### Signal/Data Levels

- **Signal levels** refers to the number of possible values a signal can have. 
- In contrast, **data levels** refer to the number of values for representing data[^3]

### Pulse/Symbol Rate

- **Pulse rate** refers to the number of symbols per second
- A pulse per bit interval exists for a number of line coding schemes. Nonetheless, it is possible to have no pulse at specific data segments.
	- For each **data element**, different line coding schemes will have a different number of **signaling elements**.
		- $r$ is ratio of the number of data elements ($N$) over a number of signaling elements ($S$).
		- $S=\dfrac{N}{r}$
- **Average signal rate**
	- Multiply the case factor ($c$, where $0<c<1$) to obtain the average signal rate
	- $S_{ave}=\dfrac{cN}{r}$

### Spectrum

- Desired characteristics:
	- Lack of high frequency components—lowers the bandwidth requirement
	- Lack of a DC component—enables the usage of transformers and capacitors for coupling
	- Concentration of power at the bandwidth's center
- **Power spectral density (PSD)**
	- Refers to the distribution of a signal's power over frequency
		- $S_{g}(f)=\lim_{ T \to \infty} \dfrac{|G_{T}(f)|^2}{T}$
			- $S_{g}$ is the PSD
			- $G_{T}$ is the signal's Fourier transform
### Clocking

-  Synchronizes the transmitter and receiver signals so that they can differentiate the symbols/bits from one another
	- Synchronize means that the phase and frequency are the same for the transmitter and receiver signal
	- The receiver must have a clock synchronized to the transmitter clock because the timing of the transmitter's output waveform is synchronized to its clock
- Clocks can provide references to determine the bit intervals of the signal
- A self-clocking code is preferred because using a separate clock line/channel is expensive
	- Without self-clocking in the coding scheme, speed is limited due to the the chances of losing synchronization and misreading data

### Error Detection

- Some line coding schemes can detect error
	- For instance, one that discerns errors through the occurrence of 2 successive positive/negative pulses
	- They are only effective when they can detect a *significant* amount of errors
- **Error detection/correction blocks** exists, hence it is not that necessary to have an error detection mechanism present in your coding scheme

### Noise Immunity

- Different coding scheme posses different noise tolerance
- The stronger the signal is relative to the noise, the better. This can be determined using the **signal to noise ratio (SNR)**
	- The SNR can mitigate the negative effects of noise by specifying requirements to be classified as a high or low signal. (i.e. it specifies at what amplitude should the signal be to be considered as high/low)
	- Lower SNR indicates lower speed, as illustrated in the bandwidth formula

### Cost and Complexity

- Some line coding schemes are more *complex* to implement, which also often means it *costs* more to carry out.

## Common Pulse Modulation Techniques

### NRZ

#### Non-Return-To-Zero Level (NRZL)

- Two different voltages for 0 and 1
- Voltage is constant in a bit interval
	- No return to zero voltage
- Usually, negative voltage for one value and positive for another (**polar**)
	- This is because using 1 and 0 (positive voltage and no voltage) will result in a positive nonzero average level, which is undesirable
		- A positive nonzero voltage corresponds to a dc signal, which is not preferred because they cannot pass in some communication circuits, does not contain information, and cost more power.
- Prevalent in digital logic systems
- $r = 1$

#### Differential NRZ Encoding (NRZ-I or NRZ-M)

- 1 is represented by a change/transition in level
- 0 is represented by no signal transition/change
- This tries to provide an error correcting property
- Used in magnetic recording
- **NRZ-S** is the inverse of this coding scheme, where 0 is represented by change and 1 is represented by staying the same (in terms of level).
- $r=1$

#### Pros and Cons

- Pros
	- Simple implementation
	- Efficiently uses bandwidth
	- Used for magnetic recording
- Cons
	- DC component
	- Asynchronous
	- Not used much for signal transmission

### Return-to-Zero (RZ)

#### Unipolar RZ

- 1 is represented by a *half-width* pulse
- 0 is represented by the absence of pulse
- Used for baseband transmission and magnetic recording
- $r=\dfrac{1}{2}$

#### Bipolar RZ

- 1 and 0 is represented by a *half-bit* pulse of opposite polarities
- A pulse is present for every bit
- Used for baseband transmission and magnetic recording
- A **self-clocking** type of signal that can provide information about the signal's frequency and phase
	- This is at the cost of *higher bandwidth*
- $r=\dfrac{1}{2}$

### Multi-level Encoding
#### Bipolar AMI (Alternate Mark Inversion)

- *Mark* means 1
- 1 is either a positive or negative pulse; it alternates between the polarities
- 0 is a no line signal
- It has error detection capabilities
- Compared to NRZ, it has no net dc component; nonetheless, it is not as efficient
- lower bandwidth than RZ
- maintains synchronization in long strings
- $r=1$

#### Pseudoternary

- The same as Bipolar AMI but alternates with 0 instead of 1; therefore, 1 is a no line signal.

[^1]: Check [[DIGDACM - Lesson 4]] for more information about baseband transmission

[^2]: Check [[DIGDACM - Lesson 4]] for more information about symbols

[^3]: For example, binary has two data levels because it uses 2 values for representing data

