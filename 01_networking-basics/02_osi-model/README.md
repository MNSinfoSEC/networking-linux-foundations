# 🧩 OSI Model

The **OSI (Open Systems Interconnection) Model** is a seven-layer conceptual framework used to understand how data is communicated across a network.

## 📚 The 7 Layers

| Layer | Name         | Main Function                                  | Examples               |
| ----- | ------------ | ---------------------------------------------- | ---------------------- |
| 7     | Application  | Provides network services to applications      | HTTP, HTTPS, DNS, SMTP |
| 6     | Presentation | Data formatting, encryption, compression       | Encoding, encryption   |
| 5     | Session      | Establishes and manages communication sessions | Session management     |
| 4     | Transport    | End-to-end delivery and port communication     | TCP, UDP               |
| 3     | Network      | Logical addressing and routing                 | IP, ICMP               |
| 2     | Data Link    | Local network communication and MAC addressing | Ethernet, MAC          |
| 1     | Physical     | Transmits raw bits through physical media      | Cables, signals, radio |

## 🧠 Layer-by-Layer Overview

### 7️⃣ Application Layer

The layer closest to the user and applications.

Examples:

* HTTP
* HTTPS
* DNS
* SMTP
* FTP
* SSH

**Data unit:** Data

---

### 6️⃣ Presentation Layer

Responsible for how data is represented and transformed.

Functions include:

* Data formatting
* Encoding and decoding
* Encryption and decryption
* Compression

**Data unit:** Data

---

### 5️⃣ Session Layer

Establishes, manages, and terminates communication sessions between applications.

**Data unit:** Data

---

### 4️⃣ Transport Layer

Provides end-to-end communication between devices.

Main protocols:

* **TCP** — Reliable, connection-oriented communication
* **UDP** — Connectionless communication with lower overhead

Also associated with **port numbers**.

Examples:

* SSH → 22
* HTTP → 80
* HTTPS → 443
* DNS → 53

**Data unit:** Segment (TCP) / Datagram (UDP)

---

### 3️⃣ Network Layer

Responsible for logical addressing and routing packets between networks.

Key concepts:

* IPv4
* IPv6
* IP addresses
* Routing
* ICMP

Common device:

* Router

**Data unit:** Packet

---

### 2️⃣ Data Link Layer

Handles communication between devices on the same local network.

Key concepts:

* MAC addresses
* Frames
* Ethernet

Common devices:

* Switch
* Network Interface Card (NIC)

**Data unit:** Frame

---

### 1️⃣ Physical Layer

Responsible for transmitting raw bits over a physical or wireless medium.

Examples:

* Ethernet cables
* Fiber-optic cables
* Radio signals
* Electrical signals

**Data unit:** Bits

---

## 🧠 Easy Memory Trick

From Layer 7 → Layer 1:

**A P S T N D P**

> All People Seem To Need Data Processing

From Layer 1 → Layer 7:

> Please Do Not Throw Sausage Pizza Away

**P → D → N → T → S → P → A**

---

## 🔐 OSI Model & Cybersecurity

Understanding the OSI model helps cybersecurity professionals identify where network activity and attacks occur.

Examples:

| Layer   | Security Relevance                            |
| ------- | --------------------------------------------- |
| Layer 7 | Web attacks, malicious requests, DNS abuse    |
| Layer 4 | Port scanning, suspicious TCP/UDP connections |
| Layer 3 | IP-based attacks, routing, firewall rules     |
| Layer 2 | MAC spoofing, ARP attacks                     |
| Layer 1 | Physical access and hardware tampering        |

For SOC analysts, Layers **2, 3, 4, and 7** are especially useful when investigating network activity.

## 🎯 What I Learned

* The purpose of the OSI model
* The seven OSI layers
* Common protocols and devices associated with each layer
* IP addresses belong to Layer 3
* MAC addresses belong to Layer 2
* Ports and TCP/UDP belong to Layer 4
* HTTP/HTTPS operate at the Application layer
* How the OSI model connects to cybersecurity

---

