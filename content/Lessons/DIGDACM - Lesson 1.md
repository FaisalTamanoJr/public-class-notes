---
title: Data Communication System Overview
draft: false
tags:
  - DIGDACM
date: 2025-05-19, 08:23
---

## Sources

1. Data Communication System Overview (Lecture Slides)
2. Class lecture

## Electronic Communications


> [!INFO]- What is Communication?
> *Communication* is the transfer of information between parties over a distance.

*Electronic communications* refers to the process of exchanging information between devices through electronic means. It aims to extend the range of communication while exerting less effort

The distance extension provided by a device is *subjective*, meaning that it is subject to various conditions such as line of sight, obstructions, and noise. For example, voice communication is not possible in a vacuum, and special devices is needed to properly implement voice communications underwater.[^1] ==Even though electronic devices allow us to overcome the barriers of communication, they are still subject to other limitations.==

One of the earliest ways to carry out long distance communications was through as *telegraphy*, wherein it follows a similar setup to the *tin can telephone* but with electrical signals instead of mechanical ones.[^2] The telegraph was a revolutionary device because it delivered information almost instantaneously over a long distance by using *Morse code*. The *walkie-talkie* also follows a similar setup but it converts the voice signals to radio waves instead.

> [!INFO] Benefits of Using Radio Transmitters and Receivers for Communication
> - They are independent of matter and can travel through a vacuum.
> - They overcome the limitation of laying out land cables between two points to facilitate long distance communications. In other words, they can also work over the sea (unlike means such as telegraphy).
> 	- Submarine cables can, however, be an alternative if the means of communication require cables.

Walkie-talkies essentially uses a similar approach to communication as the Citizen's Band (CB) radio but uses a different operating frequency.

### Basic Electronics Communications Model

It is composed of the following

- Message
- Sender
- Receiver
- Medium
- Protocol
	- The language that the sender or receiver uses

```mermaid
graph LR;

P1[Sender and Protocol] --> M[Medium]
M --> P2[Receiver and Protocol]

```

### Extended Electronic Communications Model

```mermaid
graph LR;

Source --> Transmitter
Transmitter --> Medium
Medium --> Receiver
Receiver --> Destination

```

- The *transmitter* converts the source signal into a form suited for the medium
- The *receiver* converts the received signal back into the original form of the signal

> [!EXAMPLE]- 
> The walkie-talkie sending information (transmitter) converts the voice signals into radio waves to transfer it over a longer distance. The receiving walkie-talkie (receiver) then receives the radio waves and converts it back into voice signals.

### Further Extended Electronic Communications Model

```mermaid
graph LR;

Source --> Transmitter
Transmitter --> TS[Transmission System]
TS --> Receiver
Receiver --> Destination

```

The medium is replaced into a **transmission system**. In contrast to a medium, a transmission system is a multi-point system which is practically implemented as a telephone network.

The benefits of using a transmission system:

- It can establish point-to-point communication between multiple pairs of endpoints.
	- It is possible to have different destinations with the same source (e.g., 1 person calling 2 people).
	- It is also possible to have the same destination from the same sources.

> [!EXAMPLE]-
> Workstation -> Modem -> Public Telephone Network -> Modem -> Server

## Telecommunication

Telecommunication pertains to long distance communication like telegraphy, telephone system, and AM, FM, and TV broadcasts.

## Point-to-point Communication System

Point-to-point communication is a form of communication revolving around the exchange of information between two devices at two locations.

 Microwave antennas facilitate point-to-point communication by utilizing **radio signals** or electromagnetic signals. A simplified explanation of how it works:
 
1. Transmitters convert electrical signals from the input into microwave signals.
2. The microwave signals is transferred from the transmitter to the microwave antenna through the transmission line.
3. The microwave antenna is oriented to another microwave antenna to transfer the information.
	1. The antennas must directly face each other.
	2. The alignment is crucial because radio waves generally only travel in straight lines.
4. The microwave signals is then transferred to the receiver.
5. The radio signals are converted into electrical signals.

> [!INFO] Transducers
> Antennas can be considered as *transducers* or devices that can make conversions from one form to another.

The two important electrical forms for communications:

1. Current/Voltages
2. Radio waves

Distance is a major limitation for electronic communications because receivers can only sense down to a certain level. The effect of distance on the amount of information received becomes clear when we consider that the signal strength diminishes as it gets farther away. ==Arrangements utilizing repeaters are a common workaround to counteract the distance limitation of electronics communication.== Moreover, the importance of repeaters is highlighted when we consider that the curvature of the earth also affects the distance between two microwave relay stations.

> [!TIP] Repeaters
> - Repeaters can be placed on top of obstructions, like mountains, to nullify their negative effects.
> - Repeaters can even be placed in space. In this arrangement, there is less noise and no obstruction; nonetheless, its maximum distance is its biggest limitation.

### Examples of Point-to-Point Communication Systems

1. PC connecting to devices that utilize point-to-point data communications
	- For example, a PC connected to an Arduino,[^3] which is connected to a GPRS Shield so that the Arduino can wirelessly send information to mobile devices. Besides this, the setup can also be used to establish a connection between two laptops.
2. Internet of Things - embedded applications for point-to-point communications
	- Embedded devices (usually microcontrollers) that communicate with each other. An example of a transmission system for these embedded devices would be a *GSM network*.
3. Home automation systems
	- Like Arduino with a communication link to a Bluetooth. This is by using 3 wires that serves as communication interfaces known as *Universal Asynchronous Receiver/Transmitter* (UART).
4. Drones - uses multiple communication links
	1. It is embedded system whereby it is controlled wirelessly through controllers (implying that there is a point-to-point communication occurring).
	2. Drones can also send out video information to goggles, entailing a point-to-point communication occurring between the two.

> [!INFO] 2.4 and 5 GHz
> 2.4 and 5 GHz are frequencies used for internet and drone applications because they are public bands. This means that a government license is not required to operate devices using those frequencies.

[^1]: For water communication to occur, you must be able to generate voice signals under water by vibrating the medium using your vocal cords. We normally communicate using air as the medium by modulating air pressure (compressing and expanding the surrounding air molecules). In the context of underwater communication, we can not easily generate voice signals underwater because of its effect on our capacity to breathe. 

[^2]: The tin can telephone was a longer distance communication method whereby voice signals passed to the tin can is translated to mechanical signals for transfer. When the mechanical signal reaches the other end, it is converted back to a voice signal for the other party to listen the transferred information. It is important to note that the only difference between mechanical vibration and voice signals here is the *material*—mechanical vibration involved metal, whereas voice signals was through air.

[^3]: The PC will be used to design the program for the Arduino to execute.
