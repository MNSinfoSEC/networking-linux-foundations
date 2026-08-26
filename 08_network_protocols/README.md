# 🌐 Network Protocols & Port Numbers

Network protocols are rules that define how devices communicate with each other.

Port numbers help identify the specific service or application receiving network traffic.

## 🧠 Basic Concept

text
IP Address → Which device?
Port       → Which service?
Protocol   → How they communicate?
🔑 Common Network Protocols
Protocol	Port	Purpose
FTP	20/21	File transfer
SSH	22	Secure remote access
Telnet	23	Remote access
SMTP	25	Sending email
DNS	53	Domain name resolution
DHCP	67/68	Automatic IP configuration
HTTP	80	Web traffic
POP3	110	Receiving email
IMAP	143	Email retrieval and synchronization
HTTPS	443	Secure web traffic
RDP	3389	Remote desktop
🔐 TCP vs UDP
TCP

TCP is connection-oriented and provides reliable delivery.

Common examples include:

HTTP
HTTPS
SSH
FTP
UDP

UDP is connectionless and generally has lower overhead than TCP.

Common examples include:

DNS
DHCP

A simple way to remember:

TCP → Reliable delivery
UDP → Faster, connectionless communication
🐧 Linux Commands Practiced
View Listening Ports
ss -tuln

This displays listening TCP and UDP sockets.

DNS Lookup
nslookup google.com

This can be used to query DNS information.

View HTTP Headers
curl -I https://example.com

This displays HTTP response headers.

🔐 Cybersecurity Relevance

Understanding ports and protocols is important in cybersecurity.

For example, a network scan might show:

22/tcp    open
80/tcp    open
443/tcp   open

A security analyst can investigate:

Which services are running?
Are the services expected?
Are unnecessary ports exposed?
Are services securely configured?
Are vulnerable versions being used?

Understanding network services helps with network monitoring, security assessments, and incident investigation.

🧪 Practice Questions
1. Which port does HTTPS normally use?

Answer: 443

2. Which protocol translates domain names into IP addresses?

Answer: DNS

3. Which protocol is commonly used for secure remote Linux administration?

Answer: SSH

4. Why is Telnet considered insecure compared with SSH?

Telnet sends communication without encryption, while SSH provides encrypted communication.

5. What is the difference between an IP address and a port?

An IP address identifies a device/interface on a network, while a port identifies a service or application endpoint on that device.

🎯 What I Learned
What network protocols are
What port numbers are
Common protocols and their ports
Difference between TCP and UDP
How to view listening ports in Linux
How DNS resolution works
How to inspect HTTP headers
Why ports and protocols matter in cybersecurity
