# Nmap - Network Mapper

**Category:** Network Scanning & Discovery  
**Difficulty:** Beginner to Intermediate  
**License:** Open Source (GPL)

## Description

Nmap (**N**etwork **M**apper) is one of the most powerful and widely used open-source tools for network discovery, security auditing, and reconnaissance. It is considered the industry standard for scanning networks to discover hosts, services, open ports, and potential vulnerabilities.

Security professionals use Nmap daily for:
- Asset inventory and network mapping
- Finding open ports and running services
- Operating system and service version detection
- Basic vulnerability scanning
- Penetration testing reconnaissance

## Key Features

- Host discovery
- Port scanning (TCP, UDP, SYN, ACK, etc.)
- Service version detection
- OS fingerprinting
- Nmap Scripting Engine (NSE) — over 600 scripts
- Output in multiple formats (normal, XML, grepable)
- Timing templates for stealth or speed

## Hands-on Walkthrough Examples
#### Example 1: Basic Network Discovery
- I scanned my home lab network (192.168.1.0/24) to identify live hosts and services.
- (Insert screenshot: nmap basic scan results showing discovered hosts)
#### Example 2: Detailed Service Enumeration
- Scanned a vulnerable Metasploitable 2 VM with version detection and scripting.
- (Insert screenshot: nmap -sV -sC output showing open ports, service versions, and script results)
#### Example 3: Aggressive Scan
- Used nmap -A to gather OS, services, and traceroute information.
- (Insert screenshot: Aggressive scan results)



## What I Learned

- The importance of choosing the right scan type based on the goal (speed vs. stealth vs. detail).
- How different timing templates (-T0 to -T5) affect scan results and detection risk.
- NSE scripts are extremely powerful for vulnerability detection (e.g., http-vuln-cve2017-5638).
- Aggressive scans can trigger security alerts, so they should only be used in authorized environments.

## Tips & Best Practices

- Always get explicit permission before scanning any network you do not own.
- Start with lighter scans before running aggressive ones.
- Use -oX (XML output) when integrating with other tools.
- Combine Nmap with tools like Nessus/OpenVAS for deeper vulnerability analysis.

## Resources

- Official Documentation: https://nmap.org/book/man.html
- NSE Script Database: https://nmap.org/nsedoc/
- Nmap Cheat Sheet: Search for "Nmap Cheat Sheet" (many great PDFs available)

## Common Commands

### Basic Scans

```bash
# Scan a single IP or hostname
nmap 192.168.1.105
nmap scanme.nmap.org

# Scan a range / subnet
nmap 192.168.1.1-255
nmap 192.168.1.0/24

# Version detection + default scripts
nmap -sV -sC 192.168.1.105

# Aggressive scan (OS, version, scripts, traceroute)
nmap -A 192.168.1.105

# Scan specific ports
nmap -p 80,443,22,3389 target.com

# Scan top 1000 ports (default) or all ports
nmap -p- target.com          # All 65535 ports
nmap --top-ports 100 target.com

# SYN scan (stealthy, requires root)
sudo nmap -sS 192.168.1.105

# UDP scan (slower but important)
sudo nmap -sU -p 53,123,161 target.com

# Evade basic firewalls/IDS (fragmented packets)
sudo nmap -f -T2 target.com

# Save output in multiple formats
nmap -A -oN scan.txt -oX scan.xml 192.168.1.0/24




