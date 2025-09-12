---
title: History and Overview of Embedded Systems
draft: false
tags: [EMBDSYS]
date: 2025-09-08, 15:16
---

## Sources

1. Class lecture
2. Lecture Slides

## Introduction

- An **embedded system** is hardware combined with a software with either fixed or programmable capability. It is *embedded* because it is often found inside a product, like in cars, trains, elevators, etc.
	- **hardware** - components that controller monitors and controls
	- **software** - programs that command the controller what to monitor and how to control
- It is a microprocessor or microcontroller that can be designed to perform a specific function or be made to be a part of a larger system.
- An **embedded computer system** is a programmable computer that is not general-purpose.[^5]

> [!EXAMPLE]- Examples of Embedded Computers
> - Cell phone
> - Printer
> - Automobile: engine, brakes, dash, etc.
> - Airplane: engine, flight controls, and navigation/communication
> - Digital TV
> - Household appliances

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
- All of them have chips—either microprocessor or microcontroller—with code that governs the system.

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

## Applications of Microcontrollers

Microcontrollers are embedded in devices for control. They are involved in the following areas:

- Educational robotics
- Research robots
- Helpful robots
- High-tech and aerospace use
- Process control and technical education
- Government/Peripherals office automation
- Industrial control
- Communications/Telecommunications networking
- Automotive/Transportation systems and equipment
- Consumer electronics/entertainment multimedia
- Electronic instruments/ATE/design and test equipment

## Types of Microprocessors

1. **Microcontroller**, which includes I/O devices and on-board memory
2. **Digital Signal Processor** (DSP), which are microprocessors tailored for digital signal processing
	- Requires external memory
	- Contains **Multiply-Accumulate** (MACs) units
3. Typical embedded word sizes: 8-bit, 16-bit, 32-bit

## Automotive Embedded Systems

- High-end cars may have 100 microprocessors, whereas low-end ones use 20+.
	- 4-bit microcontroller checks seat belt
	- 16/32-bit microprocessor controls engine
- *BMW 850i* brake and stability control system is comprised of the two:
	- **Anti-lock brake system (ABS)** - pumps brakes to minimize skidding
	- **Automatic stability control (ASC+T)** - controls engine for improving stability

[^5]: For this reason, PCs are not considered *embedded computer systems* despite being an essential component for producing embedded computing systems. On the other hand, a fax machine or clock made using a microprocessor is considered an embedded computing system.
[^3]: It is connected to the actuator through the **Electromechanical Backup and Safety**
[^2]: It communicates with a component outside of the microcontroller: software
[^1]: It has parts that it communicates with outside of the microcontroller, particularly the **human interface**, **diagnostic tools**, and **auxiliary systems** (for power and cooling)
[^4]: It is connected to the sensors through the **external environment**
