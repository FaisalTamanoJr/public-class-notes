---
title: DIGDACM - Lesson 4
draft: false
tags: [DIGDACM]
date: 2025-06-12, 19:31
---

## Sources

1. (Lecture Slides) Digital Signal Transmission Basics
2. Class lecture

## Data Transmission Processes

- Although data transmission and digital transmission are practically synonymous, they differ in that digital focuses more on *form*, whereas data focuses more on the *communication method* (i.e., transmitting information in the digital format).

- Top part is the transmitter side
	- Format takes in the input
	- Processes the input signal to transmit it to the medium
	- Transmitter circuit passes the information to the receiver side through the channel
- Center with two arrows is the channel or medium section[^1]
	- The medium acts like a filter
- Bottom is the receiver side
	- Produces the output signal
	- After the transmitter transmits the information using the channel, the receiver needs to amplify the information for the other circuits (like the detect circuit) to sense it.
	- Format converts and outputs it in the desired format

## Essential Transmission Approaches

- **Baseband transmission:** Converts *binary data* into *electrical pulses* for data transmission
	1. Convert input information to binary equivalent
		- If it is in text format, it is already stored in a file that is already in bytes (characters have binary equivalents). In other words, you can skip the format block when given a textual input.
			- Requires the use of an encoding scheme—such as ASCII and Unicode—to convert it to bits
		- In the contrary, analog information is more challenging to convert into digital information
			- Involves sampling, quantization, and encoding
	2. Modulate it into current or voltage pulses
	3. Transmit it to the channel
		- transmitter circuit is often an amplifier
	4. Receive the signal and demodulate/detect it back into digital information (binary values)
		- Receiving is usually done through an amplifier
	5. Decode it back to its original format
		- Received bits are converted back to the required format by the information sink
- **Bandpass transmission:** Uses *carrier signal* for data transmission, like frequency modulation and amplitude modulation
	- composed of high and low amplitude carrier signals (if binary level)

## Pulse Modulation

- Process of converting digital information, bit, or bit groups into current or voltage signals/pulses.
- Digital signals are discrete in nature

### Modulation Techniques

1. **NRZ-L** is the most basic way to represent bit values into waveforms wherein 0 means high and 1 means low (or vice versa)
2. **NRZI** is not as straight forward as NRZ-L and also includes the encoding scheme
3. **Manchester** represents bit values with two levels

## Messages and Characters

- **Analog messages** are transformed into a **sequence of bits** using a **analog-to-digital conversion** process
	- An **m-ary alphabet** specifies a set of **symbols**, wherein each symbol represents digital information in terms of a combination of **k** bits
		- high and low pulses essentially represents symbols
		- **m** represents the number of symbols
		- **k** refers to the number of bits representing each symbol
		- The more bits a symbol can carry, the better. To put it simply, the greater the **k** the better.
		- Physical signals are used to represent symbols for long distance transmission

## Transmission Characteristics

1. Signaling rate/baud rate/ symbol rate
	- The number of times a symbol changes per second
	- Expresses in **baud** (symbols per second)
2. Data rate/bit rate
	- The number of bits transmitted per second
3. Bandwidth
	- Any signals that can be decomposed into multiple sinusoidal frequencies of different frequencies (Fourier analysis). It is the span from the lowest frequency to the highest frequency.
	- Bandwidth limits the signals transmitted in a medium, and, as such, also limiting Baud Rate
	- Bandwidth is associated more with **Baud Rate** than bit rate because it is more concerned with the **symbols** involved rather than the bits.
	- **Signal Property:** Range of frequencies spanned by significant components of a signal
	- **Medium Property:** Range of frequencies that a medium can pass with no or little attenuation
	- Bandwidth can also refer to the **speed of transmission**
	- Bandwidth issues
		- A perfect sine wave only has 1 component
		- Theoretically, a square wave has infinite components if we consider an infinite amount of possible values, however the there is a limit when it is examined pragmatically
		- **Band limit**
			- Can act like a low pass filter, limiting the bandwidth into a specified frequency
			- It can alter the form of the signal (e.g., changes square wave into more sine-wave like), and therefore introduces **distortion**[^2]
		- Pulse shape affect bandwidth requirements
			- The modulation technique can reduce the duty cycle—the ratio of time when it is high compared to when it is low—to 20%.[^3]
4. Signal levels/Signal strength
	- Expressed in voltage or power units
		- It is commonly expressed in decibel units
			- dB - power relative to 1W
			- dBm - power relative to 1 mW
			- dBV - voltage level relative to 1Vrms
			- dBuV - voltage level relative to 1uVrms
		- Can also be expressed in decibel units per unit distance
			- dB/meter, dBuV/meter, etc.
5. Signal-to-noise ratio
	1. ratio of desired level to the noise signal level.
		- $SNR=\frac{\text{average signal power}}{\text{average noise power}}$
6. Data throughput
	- Effective transmission rate of useful data
	- $\text{Throughput}=\frac{\text{number of useful bits}}{\text{total transmission time}}$
7. Error rate
	- the probability that an error in transmission occurs
	- **Bit-error rate (BER)** - number of error bits per unit time
	- **Bit error ratio (BER)** - ratio of bad bits / transmitted bits measured in a time interval (to divide bits, use XOR)
	- Different signaling methods have different error rate traits
	- Negatively affects throughput and data rate

> [!TIP]- Computing for Bit Rate given Baud Rate
> 1. Find the **m** of the **m-ary**
> 2. Get $\log_{2}(m)$
> 3. Multiply $\log_{2}(m)$ with the Baud Rate

[^1]: Channel and medium are not exactly the same thing: medium is often associated with *physical* features, while a channel can be non-physical (e.g., wireless)
[^2]: To retain the actual shape of the signal, you would need to pass all significant components of the signal
[^3]: This is because it can make the square wave narrower
