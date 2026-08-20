# 📍 IP Addressing

An IP address is a logical address used to identify a device or network interface and help route network traffic.

## 🌐 IPv4

IPv4 uses **32 bits** and is written as four decimal octets.

Example:

``text
192.168.1.10
Each octet can have a value from:

0 → 255
IPv4 Structure

An IPv4 address contains:

Network portion
Host portion

The division depends on the subnet mask or CIDR prefix.

🏠 Private IPv4 Addresses

Private IPv4 addresses are used within private networks and are not directly routable on the public Internet.

The main private ranges are:

10.0.0.0/8
172.16.0.0/12
192.168.0.0/16

Example:

192.168.1.20
🌍 Public IP Addresses

Public IP addresses are globally routable addresses used for communication across the public Internet.

A home or office network commonly uses private IP addresses internally while the router communicates with the Internet using a public address.

🧩 IPv6

IPv6 was introduced to provide a much larger address space than IPv4.

IPv6 uses 128 bits.

Example:

2001:db8:85a3::8a2e:370:7334
IPv4 vs IPv6
Feature	IPv4	IPv6
Address size	32-bit	128-bit
Notation	Decimal	Hexadecimal
Example	192.168.1.10	2001:db8::1
🧮 Subnet Mask

A subnet mask determines which portion of an IPv4 address represents the network and which portion represents the host.

Example:

IP Address:    192.168.1.10
Subnet Mask:   255.255.255.0

This can also be represented using CIDR notation:

192.168.1.10/24

Subnetting will be covered in greater detail in a separate topic.

🚪 Default Gateway

A default gateway is typically the router/interface used by a device to reach destinations outside its local network.

Example:

Laptop
192.168.1.10
     ↓
Gateway
192.168.1.1
     ↓
Internet
🌎 DNS and IP Addresses

Users normally access websites using domain names rather than IP addresses.

For example:

example.com
     ↓
    DNS
     ↓
IP address
     ↓
Network communication

DNS translates domain names into IP addresses that can be used for network communication.

🔐 Cybersecurity Relevance

IP addressing is fundamental to cybersecurity and network monitoring.

Security professionals often investigate:

Source IP addresses
Destination IP addresses
Internal vs external addresses
Network ranges
Suspicious connections
Traffic between hosts

Example network information:

Source IP:       192.168.1.20
Destination IP:  203.0.113.50
Protocol:        TCP
Destination:     443

Understanding these values helps analysts investigate network activity and security alerts.

🎯 What I Learned
IPv4 uses 32-bit addresses
IPv6 uses 128-bit addresses
Difference between private and public IP addresses
Basic subnet masks and CIDR notation
Purpose of a default gateway
Relationship between DNS and IP addresses
Importance of IP addressing in cybersecurity
