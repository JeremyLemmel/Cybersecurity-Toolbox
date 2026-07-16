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
- Successfully intercepted traffic between Kali Linux and target machines (Metasploitable).
- Verified using `arp -a` on the target and Wireshark (seeing gratuitous ARP replies).
<img width="1293" height="910" alt="Screenshot 2026-07-16 120410" src="https://github.com/user-attachments/assets/57bcaa8c-80a2-4a5b-9c4f-b6ad22312a65" />
<img width="667" height="192" alt="Screenshot 2026-07-16 120426" src="https://github.com/user-attachments/assets/261fb3c9-467d-43dc-8257-57d4f826ab9a" />

<img width="1572" height="661" alt="Screenshot 2026-07-16 120439" src="https://github.com/user-attachments/assets/f32b4c1a-b5ee-4700-947d-4f532f558243" />




**Example 2: Custom Host Discovery**
- Built a Python script using Scapy to scan for live hosts on the local network (`10.0.2.0/24`).
- Used ARP requests to discover active devices.


<img width="1246" height="284" alt="Screenshot 2026-07-16 122054" src="https://github.com/user-attachments/assets/3b683adf-23e2-4f61-abe5-363a933a2410" />


<img width="491" height="196" alt="Screenshot 2026-07-16 122117" src="https://github.com/user-attachments/assets/d3d578af-c123-41f5-8bcc-6a6773d883f1" />


**Example 3: DNS Query Manipulation**
- Manually crafted and sent a custom DNS query packet for `google.com` using Scapy.
- Received and parsed the DNS response showing resolved IP addresses.
- Demonstrated low-level packet crafting and protocol understanding.


<img width="1109" height="198" alt="Screenshot 2026-07-16 123138" src="https://github.com/user-attachments/assets/381ef991-4761-4f54-bc26-f8d796e38c94" />
<img width="548" height="621" alt="Screenshot 2026-07-16 123251" src="https://github.com/user-attachments/assets/73955439-4408-4b3b-a98c-b5a3a778bee7" />



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
