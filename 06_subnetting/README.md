# 🌐 Subnetting

Subnetting is the process of dividing a larger network into smaller subnetworks.

It helps improve network organization, address management, traffic control, and security.

## 📚 What is Subnetting?

Instead of using one large network, subnetting divides it into smaller networks.

Example:

text
192.168.1.0/24
        ↓
 ┌──────┼──────┬──────┐
/26    /26    /26    /26
This allows a network to be divided into smaller sections.

🧩 CIDR Notation

CIDR notation represents the number of bits used for the network portion of an IPv4 address.

Example:

192.168.1.10/24

IPv4 contains 32 bits.

Therefore:

/24 = 24 network bits + 8 host bits

The corresponding subnet mask is:

255.255.255.0
🔢 Calculating Addresses

The number of addresses in a subnet can be calculated using:

2^host_bits

For a /24 network:

32 - 24 = 8 host bits

2^8 = 256 total addresses

Normally, two addresses are reserved:

Network address
Broadcast address

Therefore:

256 - 2 = 254 usable host addresses
📍 Example: /24

Network:

192.168.1.0/24
Type	Address
Network	192.168.1.0
First Host	192.168.1.1
Last Host	192.168.1.254
Broadcast	192.168.1.255

Total addresses:

256

Usable host addresses:

254
📍 Example: /26

Network:

192.168.1.0/26

Host bits:

32 - 26 = 6

Total addresses:

2^6 = 64

Usable addresses:

64 - 2 = 62

The four /26 subnets within 192.168.1.0/24 are:

Subnet	Network Address	Usable Host Range	Broadcast
1	192.168.1.0	.1 – .62	.63
2	192.168.1.64	.65 – .126	.127
3	192.168.1.128	.129 – .190	.191
4	192.168.1.192	.193 – .254	.255
📊 Common CIDR Examples
CIDR	Host Bits	Total Addresses	Usable Hosts
/24	8	256	254
/25	7	128	126
/26	6	64	62
/27	5	32	30
/28	4	16	14

Note: The usual usable-host calculation shown above reserves the network and broadcast addresses.

🔐 Cybersecurity Relevance

Subnetting is important in cybersecurity because networks can be separated into smaller segments.

This can help with:

Network segmentation
Access control
Firewall rules
Limiting network exposure
Isolating systems
Monitoring network traffic

For example, an organization might separate:

Employees
    ↓
Subnet A

Servers
    ↓
Subnet B

Security Systems
    ↓
Subnet C

This can reduce unnecessary communication between different parts of a network.

🎯 What I Learned
What subnetting is
How CIDR notation works
Network and host portions
How to calculate total addresses
How to calculate usable hosts
Network and broadcast addresses
Difference between /24 and /26
Basic network segmentation concepts
