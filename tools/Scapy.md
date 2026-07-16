### **Scapy**
**Category:** Network Packet Manipulation & Scripting  
**Difficulty:** Intermediate  

## Description
Scapy is a powerful Python-based library for packet manipulation. It allows you to craft, send, sniff, and analyze custom network packets at a very low level.

Security professionals and researchers use Scapy for:
- Building custom network tools and scanners
- Performing Man-in-the-Middle (MITM) attacks
- Protocol fuzzing and testing
- Developing proof-of-concept exploits

## Core Capabilities
- **Packet Crafting** — Build packets layer by layer (Ethernet, IP, TCP, UDP, DNS, ARP, etc.)
- **Sending & Receiving** — Transmit and capture packets on the wire
- **Sniffing** — Real-time packet capture and analysis
- **Automation** — Combine with Python scripting for complex attacks

## Common Workflow
1. Import Scapy in Python (`from scapy.all import *`)
2. Craft packets using layers
3. Send packets (`send()`, `sr()`, `srp()`)
4. Analyze responses and build attack scripts

## Example Usage

**Example 1: ARP Spoofing (Man-in-the-Middle)**
- Created a Python script using Scapy to perform ARP Spoofing.
- Successfully intercepted traffic between Kali Linux and target machines (Windows Server 2022 / Metasploitable).
- Verified using `arp -a` on the target and Wireshark (seeing gratuitous ARP replies).

**Example 2: Custom Host Discovery**
- Built a Python script using Scapy to scan for live hosts on the local network (`10.0.2.0/24`).
- Used ARP requests to discover active devices.

**Example 3: DNS Query Manipulation**
- Manually crafted and sent a custom DNS query packet for `google.com` using Scapy.
- Received and parsed the DNS response showing resolved IP addresses.
- Demonstrated low-level packet crafting and protocol understanding.


## What I Learned
- Deep understanding of how network protocols function at the packet level
- How easy it is to manipulate local network traffic
- Importance of network segmentation and secure protocol design

## Hands-On Learning Path
- ARP Spoofing attack against Metasploitable and another VM
- Building a simple port scanner with Scapy
- DNS spoofing demonstration in an isolated lab environment

## Resources
- Scapy Official Documentation: https://scapy.readthedocs.io/
- "Black Hat Python" by Justin Seitz (excellent Scapy examples)
