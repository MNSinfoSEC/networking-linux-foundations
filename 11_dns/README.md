# 🌐 DNS (Domain Name System)

## Overview

**DNS (Domain Name System)** is a system that translates human-readable domain names into IP addresses.

For example:

```text
www.example.com
       ↓
      DNS
       ↓
93.184.216.34

Humans can easily remember domain names, while computers communicate using IP addresses. DNS connects these two by resolving domain names to their corresponding network addresses.

🎯 Learning Objectives
Understand what DNS is
Understand why DNS is required
Learn how DNS resolution works
Understand the DNS hierarchy
Learn about different DNS servers
Understand common DNS record types
Learn about DNS caching and TTL
Understand forward and reverse DNS
Learn DNS ports and protocols
Understand recursive and iterative queries
Learn common DNS security threats
Practice DNS investigation using Linux commands
1. What is DNS?

DNS stands for Domain Name System.

It is a distributed naming system used to translate domain names into IP addresses.

For example:

google.com
    ↓
DNS
    ↓
IP Address

Instead of remembering an IP address, users can simply enter a domain name such as:

github.com

DNS then helps the computer find the IP address associated with that domain.

2. Why is DNS Important?

Without DNS, users would have to remember IP addresses for websites and services.

For example, instead of accessing:

example.com

a user would need to enter an IP address.

DNS provides a convenient naming system.

Basic process
User enters domain
        ↓
DNS lookup
        ↓
IP address obtained
        ↓
Browser connects to server
        ↓
Website loads
3. Domain Name vs IP Address
Domain Name

A domain name is a human-readable name used to identify a website or service.

Example:

example.com
IP Address

An IP address identifies a device or network interface.

Example:

192.0.2.1

DNS connects them:

Domain Name
     ↓
    DNS
     ↓
IP Address
4. DNS Hierarchy

DNS follows a hierarchical structure.

                    Root
                      |
          -----------------------
          |          |          |
         .com       .org       .net
          |
       example
          |
         www
Root

The root is at the top of the DNS hierarchy and is represented by:

.
Top-Level Domain (TLD)

Examples:

.com
.org
.net
.edu
.in
Second-Level Domain

Example:

example.com
Subdomain

Examples:

www.example.com
mail.example.com
5. DNS Servers

Different DNS servers perform different roles.

DNS Resolver

A DNS resolver receives queries from clients and helps find the required DNS information.

Computer
   ↓
DNS Resolver
Root DNS Server

Root servers direct DNS queries toward the appropriate Top-Level Domain servers.

TLD DNS Server

TLD servers handle domains under extensions such as:

.com
.org
.net
.in
Authoritative DNS Server

An authoritative DNS server contains the official DNS records for a domain.

example.com
     ↓
Authoritative DNS Server
     ↓
DNS Records
6. DNS Resolution

DNS resolution is the process of finding the IP address associated with a domain name.

For example, when a user enters:

www.example.com

a simplified DNS resolution process is:

Client
  ↓
DNS Resolver
  ↓
Root Server
  ↓
TLD Server
  ↓
Authoritative DNS Server
  ↓
IP Address

The client can then use the IP address to communicate with the destination server.

7. DNS Caching

DNS lookups can happen frequently.

To reduce unnecessary DNS queries, DNS information can be temporarily stored in a cache.

This is called DNS caching.

Caching can occur at different levels:

Browser
   ↓
Operating System
   ↓
DNS Resolver

If the required information is already available in the cache, another complete DNS lookup may not be necessary.

8. TTL (Time To Live)

DNS records contain a TTL (Time To Live) value.

TTL determines how long a DNS record can remain cached before it should be refreshed.

Example:

TTL = 3600 seconds

This represents:

3600 seconds = 1 hour
General idea
DNS Record
    ↓
Stored in Cache
    ↓
TTL expires
    ↓
Record needs to be refreshed
9. DNS Record Types

DNS uses different types of records to store different kinds of information.

A Record

Maps a domain name to an IPv4 address.

example.com
     ↓
A Record
     ↓
192.0.2.1
AAAA Record

Maps a domain name to an IPv6 address.

example.com
     ↓
AAAA Record
     ↓
IPv6 Address
CNAME Record

Creates an alias for another domain name.

Example:

www.example.com
       ↓
    CNAME
       ↓
example.com
MX Record

Specifies the mail servers responsible for receiving email for a domain.

example.com
     ↓
   MX
     ↓
Mail Server
NS Record

Specifies the authoritative name servers for a domain.

example.com
     ↓
   NS
     ↓
Name Server
TXT Record

Stores text information associated with a domain.

TXT records can be used for:

Domain verification
SPF information
Email security
Other security-related configurations
PTR Record

Used for reverse DNS lookups.

It maps:

IP Address
    ↓
Domain Name
10. Forward and Reverse DNS
Forward DNS

Forward DNS resolves:

Domain Name → IP Address

Example:

example.com
     ↓
192.0.2.1

This is the most common type of DNS lookup.

Reverse DNS

Reverse DNS resolves:

IP Address → Domain Name

Example:

192.0.2.1
     ↓
example.com

Reverse DNS commonly uses a PTR record.

11. DNS Ports and Protocols

DNS commonly uses:

UDP Port 53
TCP Port 53
UDP

UDP is commonly used for normal DNS queries because it is lightweight and fast.

TCP

TCP may be used when:

A DNS response is too large
DNS zone transfers are performed
Reliable communication is required
12. Recursive and Iterative Queries
Recursive Query

In a recursive query, the client asks a DNS resolver to find the final answer.

Client
  ↓
Resolver
  ↓
Root
  ↓
TLD
  ↓
Authoritative Server
  ↓
Final Answer
  ↓
Client

The resolver performs the lookup process on behalf of the client.

Iterative Query

In an iterative query, a DNS server provides the best information it has, such as a referral to another DNS server.

The querying system can then continue the lookup.

13. DNS and Cybersecurity

DNS is highly important in cybersecurity.

Security professionals can analyze DNS traffic to identify suspicious activity.

DNS information can help with:

Threat detection
Domain investigation
Malware analysis
Phishing detection
Network monitoring
Identifying suspicious infrastructure
Detecting potential command-and-control activity
14. Common DNS Security Threats
DNS Spoofing

DNS spoofing involves providing false DNS information to redirect users to an incorrect destination.

User
 ↓
DNS Query
 ↓
Fake DNS Response
 ↓
Malicious IP
DNS Cache Poisoning

DNS cache poisoning attempts to insert false DNS information into a DNS cache.

If successful, users may be redirected to an attacker-controlled destination.

DNS Tunneling

DNS can be abused to transfer data through DNS queries and responses.

A simplified example:

Malware
   ↓
Encoded Data
   ↓
DNS Queries
   ↓
Attacker-Controlled DNS Server

DNS tunneling can potentially be used for command-and-control communication or data exfiltration.

DNS Amplification

DNS servers can be abused in reflection and amplification attacks.

An attacker may send requests using a spoofed source address, causing responses to be directed toward a victim.

This can contribute to DDoS attacks.

15. DNS Security
DNSSEC

DNSSEC (Domain Name System Security Extensions) adds cryptographic authentication to DNS data.

It helps protect against certain forms of DNS tampering and spoofing.

DNS Filtering

Organizations can use DNS filtering to block access to known malicious or unwanted domains.

DNS Monitoring

Monitoring DNS traffic can help identify:

Suspicious domains
Unusual query patterns
Repeated failed lookups
Potential malware communication
Possible data exfiltration
16. Useful Linux DNS Commands

Linux provides several commands for investigating DNS.

nslookup

Used to perform basic DNS queries.

nslookup example.com
dig

dig provides detailed DNS information.

dig example.com

Query a specific record:

dig example.com A
dig example.com MX
dig example.com TXT
host

A simple DNS lookup command.

host example.com
17. Basic DNS Investigation

A simple DNS investigation can follow this process:

Domain
   ↓
DNS Lookup
   ↓
IP Address
   ↓
DNS Records
   ↓
Name Servers
   ↓
Mail Servers

Example:

nslookup example.com

or:

dig example.com

These commands can provide useful information about a domain.

18. DNS in a Web Request

When a user visits a website, DNS is usually involved before the browser can connect to the destination server.

A simplified process:

User enters website
        ↓
Browser / OS checks cache
        ↓
DNS query
        ↓
DNS resolver
        ↓
IP address returned
        ↓
Browser connects to server
        ↓
HTTP/HTTPS communication
        ↓
Website loads

DNS is therefore an important part of normal Internet communication.

🔐 Cybersecurity Connection

Understanding DNS is important for cybersecurity because DNS traffic can provide valuable information about network activity.

The knowledge gained here will be useful for:

DNS
 ↓
Network Traffic Analysis
 ↓
Domain Investigation
 ↓
Threat Detection
 ↓
Malware Analysis
 ↓
Security Monitoring

This knowledge will also be useful when working with tools such as Wireshark and analyzing network traffic.

🧠 Key Terms
Term	Meaning
DNS	Domain Name System
Resolver	Server that handles DNS queries
Root Server	Top level of DNS hierarchy
TLD	Top-Level Domain
Authoritative Server	Server containing official DNS records
A Record	Domain → IPv4
AAAA Record	Domain → IPv6
CNAME	Domain alias
MX	Mail server information
NS	Name server information
TXT	Text-based DNS information
PTR	Reverse DNS record
TTL	Time To Live
DNSSEC	DNS Security Extensions
📝 Practice
Basic Commands
nslookup example.com
dig example.com
host example.com
Specific Record Queries
dig example.com A
dig example.com AAAA
dig example.com MX
dig example.com NS
dig example.com TXT
✅ What I Learned
DNS translates domain names into IP addresses
DNS follows a hierarchical structure
DNS uses different types of servers
DNS resolution finds information about a domain
DNS caching reduces repeated lookups
TTL controls how long records can be cached
A and AAAA records map domains to IP addresses
CNAME provides aliases
MX records identify mail servers
NS records identify name servers
PTR records are used for reverse DNS
DNS commonly uses UDP and TCP port 53
DNS can be investigated using Linux tools
DNS is important for cybersecurity and network monitoring
