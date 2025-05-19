---
title: Data Communication System Overview
draft: false
tags:
  - DIGDACM
date: 2025-05-19, 08:23
---

> [!WARNING] 
> The content here is still **INCOMPLETE**

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

Distance is a major limitation for electronic communications because receivers can only sense down to a certain level. The effect of distance on the amount of information received becomes clear when we consider that the strength of a signal diminishes as it gets farther away. ==Arrangements utilizing repeaters are a common workaround to counteract the distance limitation of electronics communication.== Moreover, the importance of repeaters is highlighted when we consider that the curvature of the earth also affects the distance between two microwave relay stations.

[^1]: For water communication to occur, you must be able to generate voice signals under water by vibrating the medium using your vocal cords. We normally communicate using air as the medium by modulating air pressure (compressing and expanding the surrounding air molecules). In the context of underwater communication, we can not easily generate voice signals underwater because of its effect on our capacity to breathe. 

[^2]: The tin can telephone was a longer distance communication method whereby voice signals passed to the tin can is translated to mechanical signals for transfer. When the mechanical signal reaches the other end, it is converted back to a voice signal for the other party to listen the transferred information. It is important to note that the only difference between mechanical vibration and voice signals here is the *material*—mechanical vibration involved metal, whereas voice signals was through air.
