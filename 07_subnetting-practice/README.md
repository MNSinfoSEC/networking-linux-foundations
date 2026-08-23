# 🌐 Subnetting Practice & CIDR

This topic builds on basic subnetting and focuses on calculating network ranges using CIDR notation.

## 📚 What I Practiced

- Network address
- First usable host
- Last usable host
- Broadcast address
- Number of usable hosts
- Subnet ranges
- CIDR notation
- Block size

---

## 🧩 Example: /26

Given:

`text
192.168.1.0/26

Host Bits

IPv4 contains 32 bits.

32 - 26 = 6 host bits
Total Addresses
2^6 = 64
Usable Hosts

Two addresses are reserved for the network and broadcast addresses.

64 - 2 = 62 usable hosts

Therefore:

Network:       192.168.1.0
First Host:    192.168.1.1
Last Host:     192.168.1.62
Broadcast:     192.168.1.63
🧩 Example: /27

Given:

192.168.1.0/27
Host Bits
32 - 27 = 5
Total Addresses
2^5 = 32
Usable Hosts
32 - 2 = 30

Therefore:

Network:       192.168.1.0
First Host:    192.168.1.1
Last Host:     192.168.1.30
Broadcast:     192.168.1.31

The next /27 subnet starts at:

192.168.1.32
📊 /24 Divided into /27 Subnets

A 192.168.1.0/24 network can be divided into eight /27 subnets.

Subnet	Network	Usable Hosts	Broadcast
1	192.168.1.0	.1 – .30	.31
2	192.168.1.32	.33 – .62	.63
3	192.168.1.64	.65 – .94	.95
4	192.168.1.96	.97 – .126	.127
5	192.168.1.128	.129 – .158	.159
6	192.168.1.160	.161 – .190	.191
7	192.168.1.192	.193 – .222	.223
8	192.168.1.224	.225 – .254	.255
🧮 Block Size

Block size can be used to identify where the next subnet begins.

For /26:

256 - 192 = 64

Block size:

64

For /27:

256 - 224 = 32

Block size:

32

For /28:

256 - 240 = 16

Block size:

16
📊 Common CIDR Values
CIDR	Host Bits	Total Addresses	Usable Hosts
/24	8	256	254
/25	7	128	126
/26	6	64	62
/27	5	32	30
/28	4	16	14
🧪 Practice Questions
Question 1
192.168.10.0/26

Find:

Network address
First host
Last host
Broadcast
Usable hosts
Question 2
192.168.10.64/26

Find the same values.

Question 3
192.168.10.128/27

Find:

Network address
First host
Last host
Broadcast
Usable hosts
🔐 Cybersecurity Relevance

Subnetting is important for cybersecurity because networks can be divided into smaller segments.

Subnetting can help with:

Network segmentation
Firewall configuration
Access control
Traffic management
Isolating systems
Monitoring network traffic

Understanding subnet ranges also helps security analysts interpret IP addresses during investigations.

🎯 What I Learned
How CIDR notation works
How to calculate host bits
How to calculate total addresses
How to calculate usable hosts
How to find network and broadcast addresses
How to determine subnet ranges
How block size works
How subnetting supports network security
