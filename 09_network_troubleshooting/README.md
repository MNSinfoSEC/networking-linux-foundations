# 🌐 Network Troubleshooting

Network troubleshooting is the process of identifying and fixing problems that prevent devices or services from communicating correctly.

This topic introduced a systematic approach to diagnosing network connectivity problems using Linux commands.

---

## 🧠 Troubleshooting Approach

A basic troubleshooting process can be:

```text
Check Network Interface
        ↓
Check IP Address
        ↓
Check Default Gateway
        ↓
Test Local Connectivity
        ↓
Test Internet Connectivity
        ↓
Check DNS
        ↓
Check Ports / Services
1️⃣ Check IP Address
ip a

This displays network interfaces and their IP addresses.

Example:

inet 192.168.1.10/24

Here:

192.168.1.10 → IP address
/24 → CIDR prefix
2️⃣ Check Routing
ip route

This displays the system's routing table.

A common entry is:

default via 192.168.1.1

The address after default via is the default gateway.

3️⃣ Test the Default Gateway

After identifying the gateway, use:

ping <gateway-ip>

Example:

ping 192.168.1.1

This tests connectivity between the computer and its local gateway.

Stop the command with:

Ctrl + C
4️⃣ Test Internet Connectivity
ping 8.8.8.8

This tests connectivity to an external IP address.

If this works, the system can reach an external network.

5️⃣ Test DNS
ping google.com

This tests both connectivity and domain name resolution.

DNS information can also be checked using:

nslookup google.com
🔍 Understanding DNS Problems

For example:

ping 8.8.8.8       ✅
ping google.com    ❌

This can indicate that Internet connectivity is working but DNS resolution may have a problem.

This distinction is useful when troubleshooting networks.

6️⃣ Check Listening Ports
ss -tuln

This displays listening TCP and UDP sockets.

It can help identify services that are waiting for network connections.

🧰 Commands Practiced
ip a
ip route
ping <gateway-ip>
ping 8.8.8.8
ping google.com
nslookup google.com
ss -tuln
🔐 Cybersecurity Relevance

Network troubleshooting is an important cybersecurity foundation.

Security professionals need to understand normal network behaviour before identifying suspicious activity.

These commands can help investigate:

IP configuration
Network connectivity
Routing
DNS resolution
Listening services
Potential network problems

A basic investigation can follow:

Network Issue
      ↓
Check IP configuration
      ↓
Check routing
      ↓
Test connectivity
      ↓
Check DNS
      ↓
Check services and ports
      ↓
Investigate further
🎯 What I Learned
How to check IP addresses in Linux
How to view the routing table
How to identify the default gateway
How to test local connectivity
How to test external connectivity
How DNS affects network communication
How to check listening ports
How to troubleshoot network problems systematically
