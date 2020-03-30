# Network Fundamentals Notes

My notes for Network Fundamentals from Computer Networking: A Top-Down Approach.

# Chapter 1

### Road Map

* [1.1 what is the Internet?](#1.1)
* [1.2 network edge](#1.2)
  * end systems, access networks, links
* [1.3 network core](#1.3)
  * packet switch, circuit switch, network structure
* [1.4 delay, loss, throughput in networks](#1.4)
* [1.5 operations](#1.5): protocol layers, service models
* ~~1.6 networks under attack: security~~
* 1.7 history

## <a name="1.1"></a> 1.1 What is the Internet?

The textbook uses the public Internet (a speciic computer network) as their principle vehicle for discussing computer networks and their protocols. The internet can be described in two ways:
* The basic hardware and software components that make up the Internet
* A networking infrastructure that provides services to distributed applications

### 1.1.1 A "Nuts and bolts" Description

* Billions of connected computing devices
  * hosts = end systems
  * running network apps
* Communications links
  * fiber, copper, radio, satellite
  transmission rate: bandwidth
* packet switches: forward packets (chunks of data)
  * routers and switches

#### Hosts/End Systems

The Internet is a computer network that interconnects billions of computing devices throughout the world. These include traditional devices such as desktop PCs, Linux workstations and servers, as well as newer 'nontraditional' devices such as laptop, smartphones, tablets, TVs, gaming console, thermostas, home security systems, cars etc. In Internet jargon, all of these devices are called **hosts** or **end systems**. 

![Figure 1.1](fig1.1.png)

*Figure 1.1*

#### Communications Links

End systems are connected together by a network for communication links and packet switches.

[Section 1.2](#1.2) covers more about communication links, which are made up different types of physical media, including coaxial cable, copper wire, optical fibre, and radio spectrum.

#### Transmission rate

Different links can transmit at different data rates, with the **transmission rate** of a link measured in bits/second.
  
#### Packet Switches
  
When one end system has data to send to another end system, the sending end system segments the data and adds header bytes to each segment. The resulting packes of information, known as **packets**, are then sent through the network to the destination end system, where they are ressambled into the original data.

A **packet switch** takes a packet arriving on one of its incoming communication links and forwards that packet on one of its outgoing communication links.

The two most prominent types of packet switches are **routers** and **link-layer switches**. Both types of switches forward packets toward their ultimate destinations. Link-layer switches are typically used in access networks, while routers are typucalled used in the network core.

The sequence of communication links and packet switches traversed by a packet from the sending end system to the receiving end system is known as a **route** or **path** thrhough the network.

End systems access the Internet through **Internet Service Providers (ISPs)**, such as residential ISPs, corporate ISPs, university ISPs and cellular data ISPs. Each ISP is in itself a network of packet switches and communication links.

End systems, packet switches and other pieces of the Internet run **protocols** that control the sending and receiving of information within the Internet. The **Transmission Control Protocol (TCP)** and the **Internet Protocol (IP)** are two of the most important protocols in the Internet. The IP protocol specifies the format of the packets that are sent and received among routers and end systems. The Internet's principal protocols are collectively known as **TCP/IP**.

### 1.1.2 A Services Description

* **Internet**: "network of networks"
  * mobile networks
  * home networks
  * institutional networks
  * Interconnected ISPs
* **protocols** control sending, receiving of messages
  * e.g. TCP, IP, HTTP, 802.11
* **Internet standards**
  * RFC: Request for comments
  * IETF: Internet Engineering Task Force


#### Protocols

A protocol defines the format and the order of messages exchanged between two or more communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event.

A network protocol is similar to a human protocol (e.g. Person A asks for the time and Person B replies with the correct time), except that the entities exchanging messages and takign actions are hardware or software components.

#### Internet Standards

Given the importance of protocols to the Internet, it’s important that everyone agree on what each and every protocol does, so that people can create systems and products that interoperate. This is where standards come into play. **Internet standards** are developed by the **Internet Engineering Task Force (IETF)**.

The IETF standards documents are called **requests for comments (RFCs)**. RFCs started out as general requests for comments (hence the name) to resolve network and protocol design problems that faced the precursor to the Internet. RFCs tend to be quite technical and detailed. They define protocols such as TCP, IP, HTTP (for the Web), and SMTP (for e-mail). There are currently more than 7,000 RFCs.

Other bodies also specify standards for network components, most notably for network links. The IEEE 802 LAN/MAN Standards Committee, for example, specifies the Ethernet and wireless WiFi standards.

## <a name="1.2"></a> 1.2 The Network Edge

