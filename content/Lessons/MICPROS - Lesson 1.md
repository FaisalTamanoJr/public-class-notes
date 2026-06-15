---
title: Introduction to Microprocessor
draft: false
tags: ["MICPROS"]
date: 2025-06-14, 02:57
---

## Sources

1. Lecture Slides

## Practice Exercise

1. Draw a **logic diagram** of a fully-buffered CPU Module based on the **8086 microprocessor** in **minimum mode**
2. Draw a **logic diagram** of a fully-buffered CPU Module based on the **8086 microprocessor** in **maximum mode**

Draw a clock diagram:

1. clock generator
2. 8086 - connected to the octal buffer
3. 3 74LS73 - output of buffer is address bus
4. 2 74LS245 - output of transceiver is the data bus
5. 2 74LS244

## Digital Computer

### Block Diagram of the 4 Main Components of the Computer.

When the four components are combined into 1 integrated circuit, it is known as a **Microcontroller**—a complete computer system

1. Central Processing Unit - performs all the processing like arithmetic and logic operations, decision making, and control functions[^1]
	1. Control unit
	2. Processing Unit/Datapath
2. Memory Unit - store instructions and data to be processed by the program
	1. Cache Memory - fast but small, volatile[^2]
		1. Instruction Cache
		2. Data Cache
	2. Main Memory - slower but has a larger capacity than cache, volatile
		1. ROM - read only memory
		2. RWM (aka RAM) - read and write memory
	3. Secondary Memory - much slower than main memory, but very large capacity, non-volatile
		1. Hard Disk
		2. USB Flash Disk
	4. Archival Memory - very slow but very large capacity, used for backup and recovery
		1. CD/DVD
3. IO Unit - for interconnecting the environment with the computer, so allows us to interact with the computer
	1. input port
		- Peripheral devices[^3]
			- Switches
			- Keyboard
			- ADC/Data Acquisition System - allows computer to receive data coming from sensors
			- Pointing Devices (e.g., mouse)
	2. output port
		- Peripheral Devices
			- LEDs/indicator lamps
			- 7 segment/LC Display
			- DAC
			- Video Display Unit
			- Printer/Plotter
4. System bus - facilitates communication between the other three components
	- Standards that govern the system bus
		1. PLB
		2. AXI
		3. ISA
		4. PCI

## Microprocessor

- It has 3 groups of signals
	1. Address bus (M bits) - carries information to identify the component where data transfer with microprocessor will occur
		- $2^M$ - the number of addressable/accessible locations. In other words, the number of devices that can be accessed by the microprocessor
	2. Data bus (N bits) - the path where data flows to get to the desired address
	3. Control bus - governs the data transfer direction (e.g., processor to output, input to processor, etc.)
		- READ - memory -> microprocessor
		- WRITE - microprocessor -> memory
		- IO/M - InputOutput/Memory
			- 0 = microprocessor -> IO
			- 1 = microprocessor -> memory
		- RESET - brings the processor to a known starting state
		- INT
		- INTA
- The 3 signals connects it to the system bus
- Bus Cycles - 4 possible that happens in the CPU module
	1. READ - data is transferred from memory/io to microprocessor (MP)
		1. MP outputs address to address bus
		2. MP activates control for read operation
		3. Memory output data to data bus
		4. MP gets data from data bus
	2. WRITE- data is transferred from MP to memory/io
		1. MP outputs address to address bus
		2. MP outputs data to the data bus
		3. MP activates control for write operation
		4. Memory gets data from data bus and stores it to the addressed location

## Computer as a Controller Example

Composed of and are connected:

1. Microcontroller
2. Set Point
	1. Temp
	2. Time
3. Control Element
	1. Temp Sensor
	2. Heating Element
	3. Control Element

Creating this system involves **interfacing**

## 8086

- Address where first program is located - FFFF0

Recommended configuration based on the datasheet typical minimum config:

1. Microprocessor 8086
2. 8284 Clock generator
3. 2-3 Latches - separate the address signal from the data signal (demultiplexing) and maintain a constant address signal on the system bus.
4. Transceiver (transmitter transceiver) - allows data to pass in both direction. like latches but for data signals instead of address signals
5. Ram
6. PROM - contains the program that contains the control code
7. Peripheral - interconnection point between keypad and ADC

Pins that provide the 3 signals for 8284 and 8086 connection:[^4]

1. ready
2. reset
3. clock
4. S2,S1,S0
5. M/IO
6. WR
7. RD
8. BHE - enables data to the most significant half. only useful when data is 16 bit wide
9. $AD_{15}-AD_{0}$ - multiplexed (or somewhat combined) address data bus

octal latch 74LS73, look at the logic/function table to understand how it operates

octal bus transceiver SN74LS245 and SN74LS373

- look at the pin outs
- DIR determines whether it will go a to b or b to a
	- look at the function table for more info

Timing Diagram - shows the operation

- insert the clock $T_{\text{wait}}$ if you want to extend the machine/clock cycle
	- this is useful for old devices where delay is used for io devices to catch up
- **ALE** is a signal that indicates whether the signal is at state T1 or not
	- This is crucial because the multiplex address data bus contains address information during T1
	- Is connected to clock of latch
- the address/data address is the signal to be stored in the octal buffer
- left side of clock is the **read** cycle, while right is **write** cycle
- DT/R is the data transmit receive
	- active low R means that transceiver is set to receive, or data transfer is from side b to a
	- connected to DIR of transceiver
- DEN - data enable for enabling the transceiver
	- is connected to the gate enabled of the transceiver

## Minimum Mode Vs Maximum Mode

1. Minimum mode - only 1 processor
2. Maximum mode - assumes multiple processors

[^1]: Microprocessor - the combination of a control unit and a processing unit
[^2]: volatile means data is lost when power is removed
[^3]: Allows machine human interaction
[^4]: This should be coming from the 8284