# 🌐 DHCP — Dynamic Host Configuration Protocol

> **How devices get an IP address without configuring everything manually.**

DHCP is a network protocol that automatically provides devices with the network configuration they need to communicate on a network.

Instead of manually assigning an IP address, subnet mask, gateway, and DNS server to every device, DHCP can provide these settings automatically.

---

## 🧠 What Does DHCP Do?

When a device joins a network, it needs information such as:

- IP address
- Subnet mask
- Default gateway
- DNS server
- Lease duration

DHCP provides this configuration automatically.

```text
Device joins network
        ↓
Requests network configuration
        ↓
DHCP server responds
        ↓
Device receives IP configuration
        ↓
Device can communicate
🔄 The DHCP Process

The standard DHCP process is commonly remembered as:

D → Discover
O → Offer
R → Request
A → Acknowledge

        DORA
1. DHCP Discover

The client searches for available DHCP servers.

Client → DHCP Discover → Network

The client does not yet have a usable IP configuration.

The initial DHCP Discover is generally sent as a broadcast.

2. DHCP Offer

A DHCP server responds with an offer.

DHCP Server → DHCP Offer → Client

The offer can contain:

Proposed IP address
Subnet mask
Default gateway
DNS server
Lease information
3. DHCP Request

The client requests the offered configuration.

Client → DHCP Request → DHCP Server

This tells the DHCP server which configuration the client wants to use.

4. DHCP Acknowledgement

The server confirms the assignment.

DHCP Server → DHCP ACK → Client

The client can now configure its network interface and communicate using the assigned settings.

📡 DHCP Communication

DHCP normally uses:

UDP Port 67 → DHCP Server
UDP Port 68 → DHCP Client

Unlike TCP, UDP does not establish a connection before sending data.

This is useful during the initial DHCP process because a client may not yet have a usable IP address.

🏠 Example

Imagine connecting a laptop to a home Wi-Fi network.

Before receiving network configuration:

Laptop
IP Address: Not configured
Gateway:    Not configured
DNS:        Not configured

The laptop communicates with the DHCP service.

After receiving a DHCP lease:

Laptop
IP Address: 192.168.1.25
Subnet:     255.255.255.0
Gateway:    192.168.1.1
DNS:        192.168.1.1

The exact values depend on the network.

⏳ DHCP Lease

DHCP usually assigns an IP address for a limited period called a lease.

The client can use the address during the lease period.

Before the lease expires, the client can attempt to renew it.

Lease granted
     ↓
Client uses IP
     ↓
Renewal
     ↓
Lease continues

If the lease is not renewed and expires, the address can eventually be returned to the available address pool.

🗂️ DHCP Address Pool

A DHCP server usually maintains a range of addresses that it can assign.

Example:

DHCP Pool

192.168.1.100
192.168.1.101
192.168.1.102
192.168.1.103
      ↓
192.168.1.200

When devices join the network, available addresses can be assigned from this pool.

🖥️ DHCP Server vs DHCP Client
DHCP Server

Provides network configuration.

Examples include:

Router
Dedicated DHCP server
Network appliance
Server operating system
DHCP Client

Requests network configuration.

Examples include:

Laptop
Desktop
Smartphone
Virtual machine
IoT device
        DHCP Server
             │
      ┌──────┼──────┐
      ▼      ▼      ▼
   Laptop  Phone   VM
   Client  Client Client
🌐 DHCP and DNS

DHCP and DNS have different jobs.

DHCP

Provides network configuration.

DNS

Translates domain names into IP addresses.

DHCP
  ↓
"Here is your network configuration."

DNS
  ↓
"Here is the IP address for this domain."

They often work together when a device connects to a network.

🔀 DHCP Relay

DHCP uses broadcast traffic during parts of the initial process.

Routers normally do not forward broadcasts between different IP networks.

A DHCP relay agent can forward DHCP messages between a client network and a DHCP server located on another network.

Client Network
      │
      ▼
DHCP Relay
      │
      ▼
DHCP Server

This is especially useful in larger networks.

🔐 DHCP and Cybersecurity

DHCP is important from a security perspective because it controls network configuration for clients.

Security concerns include:

Rogue DHCP Server

An unauthorized DHCP server can provide malicious or incorrect network settings.

For example, it could provide:

Incorrect gateway
Malicious DNS server
Incorrect network configuration

This can potentially redirect traffic or interfere with communication.

DHCP Starvation

An attacker can attempt to consume the available DHCP address pool by making many DHCP requests.

If the pool becomes exhausted:

DHCP Pool
████████████████████ 100%

No addresses available
        ↓
Legitimate device
        ↓
Cannot obtain configuration

This can cause a denial-of-service condition.

Defensive Measures

Networks can use protections such as:

DHCP snooping
Port security
Network segmentation
Access controls
Monitoring
Switch security features
🛡️ DHCP Snooping

DHCP snooping is a network-switch security feature designed to help prevent unauthorized DHCP servers.

The switch can distinguish between:

Trusted Port
     ↓
Legitimate DHCP Server

and

Untrusted Port
     ↓
Client Devices

Unauthorized DHCP responses from untrusted interfaces can be blocked.

🔍 DHCP Investigation

Understanding DHCP can help during network troubleshooting and security investigations.

Useful questions include:

Who assigned this IP address?
What gateway was provided?
Which DNS server was provided?
How long is the lease?
Which device received the address?
Is there an unauthorized DHCP server?
🐧 Linux DHCP Commands

Depending on the Linux distribution and network manager, different commands can be used to inspect network configuration.

View IP Configuration
ip addr

or:

ip a
View Routing Information
ip route
View DNS Configuration
resolvectl status

On some systems:

cat /etc/resolv.conf

The exact DHCP client and configuration files can vary between Linux distributions and network-management systems.

🧪 Practical Exercise

Connect a Linux machine or virtual machine to a network and inspect:

1. IP Address
ip a
2. Default Gateway
ip route
3. DNS Configuration
resolvectl status

Then identify:

IP Address
Subnet
Default Gateway
DNS Server
🧩 Troubleshooting Example

Suppose a computer connects to Wi-Fi but cannot access the internet.

Check:

1. Does it have an IP address?
          ↓
2. Is the subnet correct?
          ↓
3. Is a default gateway present?
          ↓
4. Is DNS configured?
          ↓
5. Can the gateway be reached?
          ↓
6. Can an external IP be reached?
          ↓
7. Does DNS resolution work?

This creates a structured troubleshooting process instead of randomly changing settings.

🌐 DHCP vs Static IP
DHCP	Static IP
Automatically assigned	Manually configured
Easier for large numbers of devices	Requires manual management
Uses leases	Usually remains fixed
Common for client devices	Common for servers/network infrastructure
Centralized configuration	Manual or centrally managed configuration

Both approaches have legitimate uses depending on the network.

🔐 Why DHCP Matters in Cybersecurity

DHCP may look like a basic networking service, but it provides an important foundation for understanding network security.

Understanding DHCP helps with:

Network troubleshooting
Device identification
IP address management
Network monitoring
Incident investigation
Rogue-server detection
DHCP starvation awareness
Network segmentation

Before analyzing suspicious network traffic, it is useful to understand how devices receive their network configuration in the first place.

🧠 Key Concepts
DHCP
│
├── Client
├── Server
├── DORA
│   ├── Discover
│   ├── Offer
│   ├── Request
│   └── Acknowledge
│
├── IP Address
├── Subnet Mask
├── Default Gateway
├── DNS Server
├── Lease
├── Address Pool
├── DHCP Relay
└── DHCP Snooping
✅ What I Learned
 What DHCP is
 Why DHCP is used
 DHCP client and server
 DORA process
 UDP ports 67 and 68
 DHCP leases
 DHCP address pools
 DHCP relay
 DHCP and DNS relationship
 Rogue DHCP servers
 DHCP starvation
 DHCP snooping
 Basic Linux network inspection
🚀 Networking Progression
Networking Fundamentals
        ↓
OSI & TCP/IP
        ↓
IP Addressing
        ↓
MAC & ARP
        ↓
Routing
        ↓
Ports & Protocols
        ↓
Network Security
        ↓
DNS
        ↓
DHCP
        ↓
NAT & PAT
        ↓
HTTP / HTTPS
        ↓
Packet Analysis
        ↓
Practical Network Security
🔭 Next Topic

NAT & PAT

Next, I'll learn how private networks communicate with external networks and how Network Address Translation changes the way IP addresses are used.


### 📁 Your networking repo now

```text
networking/
├── ...
├── 10_network_security/
├── 11_dns/
└── 12_dhcp/
    └── README.md

This keeps the same style as your DNS README and, importantly, doesn't put “Day 12” inside the README. 🌐🔐

day 12 DHCP

Yep — Day 12 = DHCP 🌐. Since you want the README specifically for the numbered Day 12 folder, use:

12_dhcp/README.md

Here’s the polished, ready-to-paste version:

# 🌐 DHCP — Dynamic Host Configuration Protocol

> **How devices automatically receive the network configuration they need to communicate.**

---

## 📌 What is DHCP?

**DHCP (Dynamic Host Configuration Protocol)** is a network protocol that automatically assigns network configuration to devices connected to a network.

Without DHCP, network settings would have to be configured manually on every device.

DHCP can provide:

- IP address
- Subnet mask
- Default gateway
- DNS server
- Lease duration

### Simple Example

When a laptop connects to Wi-Fi:

```text
Laptop
   │
   │ "I need network configuration."
   ▼
DHCP Server
   │
   │ "Here's an available IP address."
   ▼
Laptop
   │
   ▼
Can communicate on the network
🔄 DHCP Process — DORA

The basic DHCP process is commonly remembered using DORA:

D → Discover
O → Offer
R → Request
A → Acknowledgement
1️⃣ DHCP Discover

The client searches for a DHCP server.

Client
   │
   └── DHCP Discover ──► Network

The client is essentially asking:

"Is there a DHCP server that can give me network configuration?"

2️⃣ DHCP Offer

A DHCP server responds with an available configuration.

DHCP Server
   │
   └── DHCP Offer ──► Client

The offer may contain:

Proposed IP address
Subnet mask
Default gateway
DNS server
Lease duration
3️⃣ DHCP Request

The client requests the offered configuration.

Client
   │
   └── DHCP Request ──► DHCP Server

The client indicates that it wants to use the offered configuration.

4️⃣ DHCP Acknowledgement

The DHCP server confirms the assignment.

DHCP Server
   │
   └── DHCP ACK ──► Client

The client can now configure its network interface.

Complete Flow
        CLIENT                         DHCP SERVER

           │
           │  DHCP Discover
           ├──────────────────────────►
           │
           │  DHCP Offer
           ◄──────────────────────────┤
           │
           │  DHCP Request
           ├──────────────────────────►
           │
           │  DHCP ACK
           ◄──────────────────────────┤
           │
           ▼
     Network configured
📡 DHCP Ports

DHCP uses UDP.

UDP 67 → DHCP Server
UDP 68 → DHCP Client
Why UDP?

During the initial DHCP process, the client may not yet have a usable IP address.

UDP allows DHCP communication without establishing a TCP connection first.

🏠 Real-World Example

Imagine connecting a phone to your home Wi-Fi.

The phone needs network information such as:

IP Address      → 192.168.1.25
Subnet Mask     → 255.255.255.0
Default Gateway → 192.168.1.1
DNS Server      → 192.168.1.1

Instead of entering these values manually, DHCP can provide them automatically.

⏳ DHCP Lease

DHCP normally does not assign an IP address permanently.

Instead, the address is given for a specific period called a lease.

DHCP Server
     │
     │ IP + Lease
     ▼
   Client
     │
     │ Uses IP
     ▼
Lease Renewal

The client can renew the lease before it expires.

If the lease expires and is not renewed, the address can eventually become available for another device.

🗂️ DHCP Address Pool

A DHCP server usually maintains a range of addresses that it can assign.

Example:

DHCP Address Pool

192.168.1.100
192.168.1.101
192.168.1.102
192.168.1.103
      .
      .
      .
192.168.1.200

When devices join the network, available addresses can be assigned from this pool.

🖥️ DHCP Client vs DHCP Server
DHCP Client	DHCP Server
Requests configuration	Provides configuration
Usually an end device	Usually a router/server
Receives an IP address	Maintains IP address pool
Uses UDP 68	Uses UDP 67
Examples

DHCP Clients:

Laptop
Smartphone
Desktop
Virtual machine
IoT device

DHCP Servers:

Home router
Dedicated DHCP server
Network appliance
Server operating system
🌐 DHCP and DNS

DHCP and DNS perform different jobs.

DHCP

Provides network configuration.

DHCP
↓
"Here is your IP, gateway and DNS configuration."
DNS

Translates domain names into IP addresses.

DNS
↓
"What IP address belongs to example.com?"

They often work together.

Device
  │
  ├── DHCP → Gets network configuration
  │
  └── DNS  → Resolves domain names
🔀 DHCP Relay

DHCP clients initially use broadcast communication.

Routers normally do not forward broadcasts between different networks.

A DHCP relay agent allows DHCP requests to reach a DHCP server located on another network.

Client
   │
   ▼
Client Network
   │
   ▼
DHCP Relay
   │
   ▼
DHCP Server

This is particularly useful in larger networks.

🔐 DHCP Security

DHCP is important from a cybersecurity perspective because it controls how devices receive network configuration.

Several attacks can target DHCP.

⚠️ Rogue DHCP Server

A rogue DHCP server is an unauthorized DHCP server connected to a network.

It may provide incorrect network settings.

For example:

Legitimate DHCP
      │
      ▼
Correct Gateway
Correct DNS
Correct IP

versus:

Rogue DHCP
      │
      ▼
Malicious/Incorrect Gateway
Malicious DNS
Incorrect Configuration

This can potentially redirect traffic or disrupt network communication.

💥 DHCP Starvation

DHCP starvation is an attack where an attacker attempts to consume the available DHCP address pool.

Conceptually:

DHCP Pool
████████████████████
        ↓
Many fake requests
        ↓
Addresses exhausted
        ↓
Legitimate device
        ↓
Cannot obtain an IP

This can result in a denial-of-service condition.

🛡️ DHCP Snooping

DHCP snooping is a security feature available on many managed switches.

It helps prevent unauthorized DHCP servers from responding to clients.

Ports can be classified as:

Trusted Port
     │
     ▼
Legitimate DHCP Server

and:

Untrusted Port
     │
     ▼
Client Devices

Unauthorized DHCP responses received through untrusted ports can be blocked.

🔎 DHCP in Network Investigation

Understanding DHCP can help during troubleshooting and security investigations.

Useful questions include:

Which device received this IP?
Which DHCP server assigned it?
What gateway was provided?
Which DNS server was provided?
When was the lease issued?
When will the lease expire?
Is an unauthorized DHCP server present?

DHCP logs can help correlate IP addresses with devices and lease information.

🐧 DHCP & Linux

Linux provides several commands for inspecting network configuration.

View IP Address
ip addr

or:

ip a
View Routing Information
ip route

This can show the default gateway.

Example:

default via 192.168.1.1
View DNS Configuration

On systems using systemd-resolved:

resolvectl status

Another common configuration file is:

cat /etc/resolv.conf

The exact DHCP implementation and configuration can vary between Linux distributions.

🧪 Practical Exercise

On a Linux machine or virtual machine, inspect your network configuration.

Step 1 — Find your IP
ip a

Identify:

IP Address
Subnet
Network Interface
Step 2 — Find your gateway
ip route

Identify the:

Default Gateway
Step 3 — Check DNS
resolvectl status

Identify the configured:

DNS Server
Record Your Findings
Interface:
IP Address:
Subnet:
Default Gateway:
DNS Server:
🆚 DHCP vs Static IP
DHCP	Static IP
Automatically assigned	Manually configured
Uses leases	Usually fixed
Easier for many devices	Requires configuration
Common for client devices	Common for servers
Centralized management	Manual/centralized configuration

Neither is universally better.

The choice depends on the network and its requirements.

🔐 Why DHCP Matters in Cybersecurity

DHCP may look like a simple network service, but understanding it helps build a stronger security foundation.

It is relevant to:

Network troubleshooting
IP address management
Device identification
Network monitoring
Incident investigation
Rogue DHCP detection
DHCP starvation awareness
Network access controls
Network segmentation

Understanding how a device gets onto a network is important before learning how to analyze and secure that network.

🧠 Key Concepts
DHCP
│
├── Client
├── Server
├── DORA
│   ├── Discover
│   ├── Offer
│   ├── Request
│   └── Acknowledgement
│
├── UDP 67
├── UDP 68
├── IP Address
├── Subnet Mask
├── Default Gateway
├── DNS Server
├── Lease
├── Address Pool
├── DHCP Relay
└── DHCP Snooping
