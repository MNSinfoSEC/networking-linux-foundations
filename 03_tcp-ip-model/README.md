# 🌐 TCP/IP Model


The **TCP/IP Model** is a networking framework used to describe how devices communicate across networks, including the Internet.


TCP/IP stands for **Transmission Control Protocol / Internet Protocol**.


## 📚 The 4 Layers


| Layer | Main Function | Examples |
|---|---|---|
| 4 | Application | HTTP, HTTPS, DNS, SSH, SMTP |
| 3 | Transport | TCP, UDP |
| 2 | Internet | IPv4, IPv6, ICMP |
| 1 | Network Access | Ethernet, Wi-Fi, MAC |


## 🧩 Layer-by-Layer Overview


### 4️⃣ Application Layer


Provides network services directly to applications.


Examples:


- HTTP
- HTTPS
- DNS
- SSH
- SMTP
- FTP


This layer roughly combines the Application, Presentation, and Session layers of the OSI model.


---


### 3️⃣ Transport Layer


Provides communication between applications running on different devices.


Main protocols:


#### TCP


- Connection-oriented
- Reliable
- Uses acknowledgements
- Retransmits lost data
- Uses a three-way handshake


#### UDP


- Connectionless
- Lower overhead
- Does not provide TCP-style reliability
- Useful when speed and low latency are important


The Transport layer also uses **port numbers**.


Examples:


```text
SSH    → 22
HTTP   → 80
HTTPS  → 443
DNS    → 53
2️⃣ Internet Layer

Responsible for logical addressing and routing packets between networks.

Important protocols:

IPv4
IPv6
ICMP

The main question at this layer is:

Where should this packet go?

Common device:

Router
1️⃣ Network Access Layer

Responsible for communication over the local network and physical medium.

Examples:

Ethernet
Wi-Fi
MAC addressing
Network interfaces

This layer roughly combines the Physical and Data Link layers of the OSI model.

🔄 TCP/IP Communication Flow

A simplified communication process:

Application
     ↓
Transport
     ↓
Internet
     ↓
Network Access
     ↓
     🌐 Network
     ↓
Network Access
     ↓
Internet
     ↓
Transport
     ↓
Application

For example, when accessing a secure website:

Browser
   ↓
HTTPS
   ↓
TCP
   ↓
IP
   ↓
Ethernet / Wi-Fi
   ↓
Internet
   ↓
Web Server
🔗 TCP/IP vs OSI
TCP/IP Model	OSI Model
Application	Application + Presentation + Session
Transport	Transport
Internet	Network
Network Access	Data Link + Physical

The OSI model is useful for understanding networking concepts, while TCP/IP represents the protocol architecture used for Internet communication.

🔐 Cybersecurity Relevance

Understanding TCP/IP is important for cybersecurity because network investigations commonly involve:

Source IP addresses
Destination IP addresses
Source ports
Destination ports
TCP or UDP
Network protocols
Network connections

For example:

Source:      192.168.1.20:49152
Destination: 142.250.x.x:443
Protocol:    TCP
Service:     HTTPS

Understanding these values helps security professionals analyze network traffic and identify unusual communication.

🎯 What I Learned
What the TCP/IP model is
The four TCP/IP layers
The purpose of each layer
Differences between TCP and UDP
How IP addressing and routing work within the model
How TCP/IP relates to the OSI model
Why TCP/IP knowledge is important for cybersecurity
