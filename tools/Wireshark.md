# Wireshark - Network Protocol Analyzer

**Category:** Packet Capture & Analysis  
**Difficulty:** Beginner to Intermediate  

## Description

Wireshark is the world’s most popular network protocol analyzer. It allows you to capture and interactively browse traffic running on a computer network in real time.

## Key Features
- Deep inspection of hundreds of protocols
- Powerful display filters
- Live packet capture and offline analysis
- VoIP analysis, decryption support (SSL/TLS with key)
- Rich visualization (IO graphs, conversations, endpoints)

## Hands-on Examples
#### Example 1: Basic HTTP Traffic Analysis
- Captured traffic while browsing a website and analyzed HTTP requests/responses.
- (Insert screenshot: Wireshark showing HTTP packets with request details)
#### Example 2: DNS Query Analysis
- Filtered DNS traffic to observe domain resolution.
- (Insert screenshot: DNS filter results)
#### Example 3: Following TCP Streams
- Used "Follow → TCP Stream" to reconstruct a full conversation.



## What I Learned
- How to quickly isolate relevant traffic using filters
- Importance of understanding the TCP 3-way handshake
- How sensitive data can be exposed if not properly encrypted

## Resources
- Official Documentation: https://www.wireshark.org/docs/
- Wireshark Wiki & Sample Captures



## Common Filters & Commands

```bash
# Capture filter examples (applied during capture)
tcp port 80 or tcp port 443
host 192.168.1.105
not arp and not icmp

# Display filter examples (applied after capture)
http
dns
tcp.port == 443
http.request.method == "POST"
frame contains "password"
