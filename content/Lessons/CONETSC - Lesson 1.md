---
title: Introduction to Computer Networks
draft: false
tags: [CONETSC]
date: 2025-09-17, 02:16
---

## Sources

1. Class Lecture

## Introduction

- Applications are network components that make it easy for laymen to access the internet
- The way applications use the network relates to *services*, whereas the way networks support applications relates to *hardware* and *software*

## Fundamental View of the Internet (or **Hardware and Software** View)

- **Internet** is a loosely hierarchical network of networks, comprising of interconnected ISPs
- A **network** refers to the whole set of connected devices, routers, and links. Organizations are responsible for managing different networks.
- **Internet Service Providers** (ISPs) connect devices to content providers
- It is composed of countless computing devices known as the **hosts** or the **end systems**. They are referred to as hosts or end systems because of their location: the edge of a network.
	- Hosts consists of clients and servers[^12]
	- Servers are usually found in data centers—places often tethered with high speed CPUs (for fast processing) and switches. Data centers require a lot of energy for storage; hence, it is frequently placed near bodies of water for easier heat dissipation.
- **Peering** is the process where an ISP connects to another ISP to access content providers that they do not have a direct connection with
- **Communication links** and **packet switches** are key components that are responsible for connecting end systems to the network
	- communication links - correspond to physical media like a UTP copper cable, optical fiber, coaxial table, satellite,[^7] or wireless (through radiospectrum). Choosing the right physical media is important because it determines the **data transmission rate**[^8]
		- **access networks** - are physical networks that connect clients to the nearest **edge routers**—routers which are nearest to the clients or servers, and ISPs. They are made up of **physical media**, which is either wired or wireless communication links.
			- edge routers can be categorized as *residential access networks* (home), *institutional access networks* (work and school), and *mobile access networks* (4G/5G and Wi-Fi).
			- Physical media can be categorized as **guided** or **unguided**
				- guided - physical facilities guides the electromagnetic signals to the destination. They are better for *troubleshooting* because it makes it easier to pinpoint the cause of the error.
				- unguided - no physical facilities are not used to guide the electromagnetic signals to the destination. They are better for *longer distances* because it is not constrained by the cable length.[^13]
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
	- In particular, they define the format, order of messages sent and received, receipt, and actions taken during message transmission.
	- Examples are HTTP, TCP, IP, FTP, and PPP
	- 2 most important internet protocols
		1. **Internet Protocol** (IP) - specifies the packet format. The format allows the switches in its path to identify it.
		2. **Transmission Control Protocol** (TCP)
	- HTTP (Hyper Text Transfer Protocol) - used for accessing the web
	- FTP (File Transfer Protocol) - for file transfer
	- SMTP (Small Mail Transfer Protocol) - for sending and receiving emails
	- **IEEE 802.11** - the Wi-Fi or wireless protocol
	- **IEEE 802.15** - the Bluetooth protocol
	- IEEE 802.15.4 - the Zigbee protocol
	- IEEE 802.16 - WiMAX
- Internet standards
	- Standards are usually in the form of **RFCs** (Request for Comments) and are developed by the **IETF** (Internet Engineering Task Force)
	- IETF - are a group of engineers and researchers from the academe and industry which develop standards for the internet
		- working group - IETF members are responsible for creating standards which will immediately be used once released
		- research group - IETF members which develops standards to be forwarded to the working group for formalization and deployment
	- Once standards are in the form of RFCs, they are officially recognized and manufacturers ought to adhere to them

## **Service** View of the Internet

- **Communication infrastructure** enables distributed applications such as the web, email, messaging, social media, etc.[^10]
	- Note that ==applications run on end systems== and not on the **network core** (i.e., internal components of the internet like switches, routers, and link layer switches)
	- The **network core** are interconnected routers that make up the network of networks
- When developing a distributed application, the application should have instructions revolving around how the end system connects to the internet and how it can access content from a particular server. **API** (Application Programming Interface) is a platform that facilitates this process.[^11]
	- APIs also specify rules so that the sender can deliver information to a desired receiver. In other words, it provides services to allow us to interact with the internet.
	- **hooks** - enables data delivery and reception
	- **connect** - the use of the internet transport service
- Communication services provided to apps can be of two modes:
	- connection-oriented reliable
	- connectionless unreliable

## Access Networks

- **cable-based access**
	- residential access networks often use **broadband** for sending multiple messages (in contrast to baseband, which is used for single transmission). Broadband can be differentiated as either cable or DSL.
		- the cable headend provides a connection between the client to the nearest edge network and ISPs
		- **cable** - a coaxial cable or fiber optic cable guides the signal coming from the **cable headend** (the end where the cable company is located) to the service subscribers. Inside the subscribers’ home, there is a splitter to distribute the signal to both the TV and the cable modem.
			- The cable modem is an analog to digital converter
			- The data sent by the cable modem must be converted into digital for transmission purposes
			- **cable modem termination system** (CMTS) - the cable headend’s digital to analog converter
			- The splitter distributes video and audio data to the TV, while distributing information to the cable modem. It utilizes **multiplexing** to send multiple signals over a single physical channel.[^14] There are two ways to multiplex.
				1. **frequency division multiplexing** (FDM) - divides the medium into multiple channels by using different frequencies. Often used for analog signals.
				2. **time division multiplexing** (TDM) - divides the medium into multiple channels by using different time. A bandwidth in this type is divided into time segments (called **epoch**). Only used for digital signals because analog signals cannot be stopped (they must be continuous) while digital signals can be stopped anytime due to its *discrete* nature.
			- The multiple and simultaneous distribution of data entails that there is a high likelihood that the subscribers would not experience the maximum capacity of the physical media. However, if they are accessing different servers (e.g., one client is accessing Facebook while another client is accessing YouTube), it is possible for some of them to still reach the maximum capacity.
			- In a multiple accessing situation (i.e., multiple clients accessing the same server over one physical media), the biggest challenge is avoiding **collision**.
				- One way of mitigating it is through **protocols**. For example, the **hybrid fiber coax** (HFC), which is a cable combining coaxial with fiber optic.[^15]
					- 40 Mbps to 1.2 Gbps downstream transmission rate
					- 30 to 100 Mbps upstream transmission rate
- **digital subscriber line** (DSL)
	- **DSL access multiplexer** (DSLAM) - uses a coaxial cable and also converts analog to digital signals. It is mainly used to connect telephone lines to the central office
		- data moving across the DSL phone line is for the internet
		- voice moving across the DSL phone line is for the telephone network
	- 24-52 Mbps downstream transmission rate
	- 3.5-1.6 Mbps upstream transmission rate
	- can possess both an ISP and a telephone network at the same time[^16]
	- the **DSL modem** is where the wireless and LAN ports are located..[^17] It also converts analog signals to digital signals
	- The central office provides the power to the telephone network
	- **Asymmetric DSL** is used for residential areas because ISPs provide multiple subscription packages
- **home networks**
	- **access point** - converts LAN to wireless LAN
	- Cable or DSL modem - modern ones often incorporate access points already
	- Ethernet - a LAN technology which has a higher capacity than the usual LAN cables (e.g., UTP and STP)
	- Router is usually found outside, going to the cable headend (if cable-based) or central office (if DSL)
- **wireless access networks**
	- **Wireless local area networks** (WLAN)
		- 802.11b/g/n (Wi-Fi) - 11, 54, 450 Mbps transmission rate
		- Inside or around building (~100 ft)
	- **Wide-Area cellular area networks** (WLAN)
		- 4G - 10‘s Mbps
		- Provided by cellular network operator (~10 km)
	- 5 GHz - high capacity, low coverage
	- 2.4 GHz - low capacity, high coverage
	- Using mobile data -> phone looks for the closest **Base Station**
	- **Mobile Station** - phone with a Subscriber Identity Module (SIM) card
	- 3G - SMS, Call, and multimedia
	- 2G - SMS and Call
	- 2.5G (or edge) - Kbps data rate
- **enterprise networks**
	- are generally larger because they are used by universities and companies
	- comprised of wired and wireless technologies. It also mixes switch and routers
		- Ethernet: 100 Mbps, 1 Gbps, 10 Gbps
		- Wi-Fi: 11, 54, 450 Mbps
- **data center networks**
	- have high bandwidths, links between 10s to 1000s Gbps. They connect countless of servers to the internet.

[^12]: Clients are usually content requesters, while servers are usually content providers
[^7]: Helpful for remote areas where it is not likely to have cellular or mobile towers (like disaster prone areas)
[^8]: This rate is directly proportional to the **bandwidth**.
[^13]: Take note that a longer channel (like the cable length) will result in higher resistance
[^1]: headers are placed at the *MSB* (most significant bit), while trailers are placed at the *LSB* (least significant bit)
[^2]: For instance, parity bits for headers
[^5]: These are used in LAN (local-area network) applications
[^6]: These have larger scale application compared to link layer switches (e.g., ISPs and wide-area networks)
[^9]: A weaker signal energy is undesirable because it can prevent the information from reaching its destination
[^3]: Segments exists after headers and trailers are connected with the bits
[^4]: **Addressing** are added to packets to identify the desired destination. An example of addressing is IP (or logical addressing)
[^10]: *Distributed* applications refer to applications enable the exchange of data between multiple end systems.
[^11]: APIs specify how programs from multiple end systems can use the network core to exchange information. This necessitates that the same APIs are installed/running on the different communicating end systems.
[^14]: The medium becomes to what’s known as a *shared medium* because it is now composed of multiple signals sharing the same physical channel
[^15]: It provides asymmetric transmission rates, that is, upstream and downstream transmission rates are unequal. Cable providers often offer asymmetric packages only
[^16]: unlike cable-based access which relies on an agreement with an ISP (not their own)
[^17]: The ports help connect the end systems to the DSL internet