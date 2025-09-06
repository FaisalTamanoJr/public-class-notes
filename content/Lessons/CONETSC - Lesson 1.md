---
title: Introduction to Computer Networks
draft: false
tags: [CONETSC]
date: 2025-09-06, 22:28
---

## Sources

1. Class Lecture

## Introduction

- Applications are network components that make it easy for laymen to access the internet
- The way applications use the network relates to *services*, whereas the way networks support applications relates to *hardware* and *software*

## Fundamental View of the Internet (or **Hardware and Software** View)

- **Internet** is a loosely hierarchical network of networks
- It is composed of countless computing devices known as the **hosts** or the **end systems**. They are referred to as hosts or end systems because of their location: the edge of a network.
- **Communication links** and **packet switches** are key components that are responsible for connecting end systems to the network
	- communication links - correspond to physical media like a UTP copper cable, optical fiber, coaxial table, satellite,[^7] or wireless (through radiospectrum). Choosing the right physical media is important because it determines the **data transmission rate**[^8]
		- When the sending end system has no data to send to another end system, it segments the data and adds two bytes of **headers** and **trailers** per segment.[^1]
			- headers and trailers are used to ensure synchronization[^2]
		- Data is transmitted in the form of electromagnetic signals
		- The physical media chosen should be able to accommodate the amount of data to be sent
	- packet switches - receives packets from one of its incoming links and forwards it to one of its outgoing links, thereby functioning as an inbound and outbound port
		- An important mechanism in networks is their capacity to have switches that manages the routing path of its packets so that information can properly be sent from source to destination.
		- layer 2 packet switch: link layer switch[^5]
		- layer 3 packet switch: router switch[^6]
	- Greater **bandwidth** means more information sent in a specified unit of time; however, it also means that noise is potentially greater and therefore weaker signal energy[^9]
- **Routers** are switches that direct received information to desired destination
	- The information must be converted into packets in order for routers to send the data to the desired destination. In short, the information goes through the following stages of conversion: ==analog data -> bits (or digital data) -> segments[^3] -> packets[^4]==. These steps guarantees that data integrity is maintained and that it arrives at the correct destination.
	- Routers are primarily used to examine the headers and addressing of incoming packets and forward it to an outbound link.
- **Route** or **path** refers to the communication links and switches that the packet needs to traverse to reach its desired endpoint
- **Protocols** controls how messages are received and sent. They are necessary for establishing consistent communication quality by defining specific standards. Moreover, it also ensures *interoperability*—the characteristic of a system to properly work with other systems.
	- Examples are HTTP, TCP, IP, FTP, and PPP
	- 2 most important internet protocols
		1. **Internet Protocol** (IP) - specifies the packet format. The format allows the switches in its path to identify it.
		2. **Transmission Control Protocol** (TCP)
	- HTTP (Hyper Text Transfer Protocol) - used for accessing the web
	- FTP (File Transfer Protocol) - for file transfer
	- SMTP (Small Mail Transfer Protocol) - for sending and receiving emails
- Internet standards
	- Standards are usually in the form of **RFCs** (Request for Comments) and are developed by the **IETF** (Internet Engineering Task Force)
	- IETF - are a group of engineers and researchers from the academe and industry which develop standards for the internet
		- working group - IETF members are responsible for creating standards which will immediately be used once released
		- research group - IETF members which develops standards to be forwarded to the working group for formalization and deployment
	- Once standards are in the form of RFCs, they are officially recognized and manufacturers ought to adhere to them

## **Service** View of the Internet

- **Communication infrastructure** enables distributed applications such as the web, email, messaging, social media, etc.[^10]
	- Note that ==applications run on end systems== and not on the **network core** (i.e., switches like routers and link layer switches)
- When developing a distributed application, the application should have instructions revolving around how the end system connects to the internet and how it can access content from a particular server. **API** (Application Programming Interface) is a platform that facilitates this process.[^11]
	- APIs also specify rules so that the sender can deliver information to a desired receiver
- Communication services provided to apps can be of two modes:
	- connection-oriented reliable
	- connectionless unreliable

[^7]: Helpful for remote areas where it is not likely to have cellular or mobile towers (like disaster prone areas)
[^8]: This rate is directly proportional to the **bandwidth**.
[^1]: headers are placed at the *MSB* (most significant bit), while trailers are placed at the *LSB* (least significant bit)
[^2]: For instance, parity bits for headers
[^5]: These are used in LAN (local-area network) applications
[^6]: These have larger scale application compared to link layer switches (e.g., ISPs)
[^9]: A weaker signal energy is undesirable because it can prevent the information from reaching its destination
[^3]: Segments exists after headers and trailers are connected with the bits
[^4]: **Addressing** are added to packets to identify the desired destination. An example of addressing is IP (or logical addressing)
[^10]: *Distributed* applications refer to applications enable the exchange of data between multiple end systems.
[^11]: APIs specify how programs from multiple end systems can use the network core to exchange information. This necessitates that the same APIs are installed/running on the different communicating end systems.
