# 🐧 Linux Networking

Linux provides several command-line tools for viewing and troubleshooting network configuration and connectivity.

## 📚 What I Learned

- Network interfaces
- IP addresses
- Routing
- Connectivity testing
- DNS lookup
- Listening ports
- Network sockets

---

## 🌐 Checking IP Addresses

```bash
ip a

Displays information about network interfaces and their IP addresses.

Example:

inet 192.168.1.10/24

Here:

192.168.1.10 → IP address
/24 → CIDR prefix
🔌 Network Interfaces
ip link

Displays available network interfaces.

A common interface is:

lo

lo is the loopback interface and commonly uses:

127.0.0.1
🛣️ Routing Table
ip route

Displays the system's routing table.

Example:

default via 192.168.1.1

The default gateway is the device used to reach networks outside the local network.

📡 Testing Connectivity
ping google.com

ping can be used to test whether a destination is reachable.

It uses ICMP.

Stop the command using:

Ctrl + C
🔎 DNS Lookup
nslookup google.com

This can be used to query DNS information and find IP addresses associated with domain names.

🔐 Checking Listening Ports
ss -tuln

This displays listening TCP and UDP sockets.

It can help identify services listening for network connections.

🧰 Commands Practiced
ip a
ip link
ip route
ping google.com
nslookup google.com
ss -tuln
🔐 Cybersecurity Relevance

Linux networking commands are useful for security monitoring and troubleshooting.

They can help identify:

IP addresses
Active network interfaces
Default gateways
Network routes
DNS information
Listening ports
Network services

A basic investigation can follow:

Network Activity
       ↓
Check IP address
       ↓
Check interfaces
       ↓
Check routing
       ↓
Check connections
       ↓
Check listening ports
       ↓
Investigate suspicious activity
🎯 What I Learned
How to view IP addresses
How to identify network interfaces
How to view routing information
How to test connectivity
How DNS lookup works
How to view listening ports
How Linux networking commands can support cybersecurity investigations
