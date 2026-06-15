---
title: Tools, Standards, and Constraints for Embedded Systems
draft: false
tags: [EMBDSYS]
date: 2025-09-13, 01:07
---

> [!WARNING]
> Still Incomplete/TODO

## Sources

1. Class lecture
2. Lecture Slides

## Simulators

- Software that copies the behavior of embedded systems on a host machine
- Advantages
	- It can save time and costs because it does not require hardware
	- Helpful during early-stage development and debugging
	- Safety when designing embedded systems with potentially dangerous operations
- Disadvantages
	- It represents the *ideal* situation, so it may not accurately reflect the behavior in the real-world
	- It cannot simulate all real-world conditions
	- Hardware-specific bugs may remain invisible
- Examples
	- Proteus - combines circuit simulation with microcontroller simulation.
	- MPLab - it is used for simulating PIC microcontroller code
	- Tinkercad - online simulator for Arduino and basic electronic circuits
	- Keil $\mu$Vision Simulator - used for simulating ARM-based embedded systems
	- AVR Simulator - for simulating AVR microcontrollers
	- SimulIDE - simple, real-time simulator for electronics and PIC/AVR microcontrollers
	- PICSsimLab - an open-source simulation tool designed for microcontroller-based electronic circuits, primarily focusing on PIC microcontrollers
	- Wokwi - online simulator to simulate Arduino, ESP32, STM32, and other microcontrollers

## Emulators

- Tools that replicate the functionality closer than simulators. Unlike simulators, its not limited to software only.
- Advantages
	- Real-time debugging capability
	- Accurate hardware behavior reproduction
	- Can monitor program flow and memory in real-time
	- Support breakpoints and step-by-step execution
- Disadvantages
	- more expensive than simulators
	- Requires specialized hardware
- Examples
	- ARM Dstream
		- emulator for ARM-based systems
		- MPlab real ice
		- Keil
		- Atmel-Ice
		- Segger J-link

## Compilers

- components
	- preprocessor
	- compiler
	- assembler
	- linkers
