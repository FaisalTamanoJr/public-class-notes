---
title: History and Overview of Embedded Systems
draft: false
tags: [EMBDSYS]
date: 2025-09-08, 15:16
---

> [!NOTE] TODO
> 1. [x] Part 1 (until page 23)
> 2. [ ] Part 2 (until page 41)

## Sources

1. Class lecture
2. Lecture Slides

## Introduction

- An **embedded system** is hardware combined with a software with either fixed or programmable capability. It is *embedded* because it is often found inside a product, like in cars, trains, elevators, etc.
	- hardware - components that controller monitors and controls
	- software - programs that command the controller what to monitor and how to control
- It can designed to perform a specific function or it can be made to be a part of a larger system.

## History

| Date       | Key Event                                                                                                                                                                                                                                 |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1960       | The **Apollo Guidance System** was the first to utilize an embedded system                                                                                                                                                                |
| 1965       | The **Minuteman Missile Guidance System** used a computer called the **D-17B**                                                                                                                                                            |
| 1968       | The **Volkswagen 1600** was released and it was the first vehicle to use an embedded system                                                                                                                                               |
| 1971       | - **Texas Instruments** engineers, **Gary Boone** and **Michael Cochran**, made the first microcontroller/microcomputer<br><br>- September 17: the **TMS1802NC**, a single-chip microcontroller, was used for a four-function calculator. |
| 1987       | The release of the first embedded OS, **VxWorks**                                                                                                                                                                                         |
| 1996       | The release of Microsoft’s Windows embedded CE                                                                                                                                                                                            |
| late 1990s | The release of the first embedded Linux system                                                                                                                                                                                            |
| 2013       | $140 billion achieved by the embedded market                                                                                                                                                                                              |

## Characteristics of an Embedded System

- Designed for a specific task (as opposed to general tasks such as playing video games, editing documents, etc.)
- Connected with peripherals to connect with input and output devices
- Runs in *real-time*
- Minimal user interface
- Limited memory (no secondary memory), less power consumption, and low cost
- They have chips

## Typical Embedded System Structure

1. Sensor[^3]
2. Microcontroller
	1. ADC
	2. Memory[^2]
	3. FGPA and ASIC (Application-Specific Integrated Circuit)
	4. CPU (or Microprocessor)[^1]
	5. DAC
3. Actuator[^4]

## Microprocessor Vs Microcontroller

| Microprocessor                                               | Microcontroller                                           |
| ------------------------------------------------------------ | --------------------------------------------------------- |
| Functional blocks: register, ALU, timing, and control units  | Functional blocks: RAM, timer, parallel I/O, ADC, and ADC |
| Uses external memory                                         | Data and code is inside the microcontroller               |
| For general-purpose computer systems                         | For application-specific dedicated systems                |
| For multitasking                                             | Single-task oriented                                      |
| Freedom in choosing the number of memory or I/O ports needed | Memory or I/O is fixed and tailored to a specific task    |
| Heavy and high cost                                          | Lightweight and low cost                                  |
| More space and power needed                                  | Less space and power needed                               |

> [!Info] Microcontrollers
> - They are *single chip* computers made to read input devices, process data, and control output devices.
>  - They execute only a single application
>  - They run on a single integrated circuit, consisting of a CPU, RAM, ROM, and I/O ports

## Prominent Microcontroller Manufacturers

| Manufacturer            | Description                                                                                                                                                                                                                                                                                        |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Microchip Technology    | - Microchip Technology was widely known for their 8-bit, 16-bit, and 32-bit PIC microcontrollers<br><br>- **PIC microcontrollers** were popular because they were easy to use, were widely available, and offered countless of support resources.                                                  |
| Atmel                   | - They are currently acquired by Microchip<br><br>- They were known for their 8-bit microcontrollers, the **AVR family**. These were flexible and did not consume much power.                                                                                                                      |
| Cypress Semiconductor   | - They are currently acquired by Infineon Technologies<br><br>- They were known for microcontrollers which included the **PSoC** (Programmable System-on-Chip) family. These microcontrollers were highly customizable and flexible due to their integrated programmable analog and digital blocks |
| Espressif Systems       | They offered the **ESP8266** and **ESP32**, which were popular because they were Wi-Fi and Bluetooth modules and SoCs that had built-in wireless connectivity (ideal for IoT applications)                                                                                                         |
| Freescale Semiconductor | They offered the **ColdFire** and **Kinetis** microcontroller families. These were used for applications including automotive to industrial control.                                                                                                                                               |
