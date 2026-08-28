# 🔐 Network Security Basics

Network security focuses on protecting networks, devices, services, and data from unauthorized access, misuse, and attacks.

This lesson introduced some fundamental network security concepts and common threats.

---

## 📚 What I Learned

- Firewalls
- Network threats
- Phishing
- Network sniffing
- Port scanning
- DoS and DDoS
- Encryption
- Authentication
- Authorization

---

## 🔥 Firewall

A firewall controls network traffic based on predefined security rules.

It can allow or block traffic based on:

- IP addresses
- Ports
- Protocols
- Direction of traffic

Example:

```text
Internet 🌐
     ↓
[ Firewall 🔥 ]
     ↓
Computer 💻

A firewall can help prevent unwanted network connections.

🎣 Phishing

Phishing is a social engineering technique where an attacker attempts to trick a user into revealing sensitive information.

Example:

"Your account has been locked.
Click here to verify your account."

Phishing can occur through:

Email
Messages
Fake websites
Social media
Malicious links
👀 Network Sniffing

Network sniffing involves capturing and analyzing network traffic.

Encryption is important because it helps protect sensitive information from being easily read if traffic is intercepted.

🚪 Port Scanning

Port scanning is the process of checking which network ports are open or accessible on a system.

Example:

22   → SSH
80   → HTTP
443  → HTTPS

Open ports are not automatically vulnerabilities, but they can reveal services running on a system.

💥 DoS and DDoS
DoS

Denial of Service (DoS) attempts to make a service unavailable by overwhelming or disrupting it.

DDoS

Distributed Denial of Service (DDoS) performs a similar attack using traffic from multiple systems.

💻 →
💻 →     🌐 Server
💻 →       💥
💻 →

The objective is generally to make the service unavailable to legitimate users.

🔐 Encryption

Encryption transforms readable information into protected data.

Plaintext
    ↓
Encryption 🔐
    ↓
Ciphertext
    ↓
Decryption 🔑
    ↓
Plaintext

HTTPS uses encryption to help protect web communication.

HTTP  → Port 80
HTTPS → Port 443 🔐
👤 Authentication vs Authorization

These are two important security concepts.

Authentication

Authentication answers:

Who are you?

It verifies a user's identity.

Examples:

Username and password
Multi-factor authentication
Biometrics
Authorization

Authorization answers:

What are you allowed to do?

It determines what an authenticated user can access or perform.

Easy way to remember
Authentication → Identity
Authorization  → Permissions
🐧 Linux Commands Practiced
Check listening ports
ss -tuln
Check IP information
ip a
Check routing information
ip route

These commands can help understand the network configuration of a Linux system.

🔐 Cybersecurity Relevance

Understanding network security fundamentals is important before moving into more advanced cybersecurity topics.

Security professionals need to understand:

Which services are exposed
Which ports are listening
How network traffic is protected
How attackers may target network services
How authentication and authorization work
How firewalls control network traffic

A basic security mindset is:

Identify
   ↓
Understand
   ↓
Protect
   ↓
Monitor
   ↓
Investigate
🎯 What I Learned
How firewalls control network traffic
What common network threats look like
What phishing is
What network sniffing means
What port scanning is
Difference between DoS and DDoS
Why encryption is important
Difference between authentication and authorization
How Linux commands can help inspect network configuration
