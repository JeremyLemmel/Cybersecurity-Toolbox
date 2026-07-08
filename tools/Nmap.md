
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
- I scanned my home lab network (10.0.2.0/24) to identify live hosts and services.
 <img width="987" height="984" alt="Screenshot 2026-07-07 140317" src="https://github.com/user-attachments/assets/62e27ab9-3843-4db2-a7e7-6a8ff3686deb" />

#### Example 2: Detailed Service Enumeration
- Scanned a vulnerable Metasploitable 2 VM with version detection and scripting.
 <img width="984" height="884" alt="Screenshot 2026-07-08 121330" src="https://github.com/user-attachments/assets/4f1afe91-77ce-457b-937f-2736596e141c" />

#### Example 3: Aggressive Scan
- Used nmap -A to gather OS, services, and traceroute information.
 <img width="1226" height="854" alt="Screenshot 2026-07-08 122851" src="https://github.com/user-attachments/assets/5bd1091d-c700-4c99-8dec-efc86282f78d" />



## What I Learned

- The importance of choosing the right scan type based on the goal (speed vs. stealth vs. detail).
- How different timing templates (-T0 to -T5) affect scan results and detection risk.
- NSE scripts are extremely powerful for vulnerability detection (e.g., http-vuln-cve2017-5638).
- Aggressive scans can trigger security alerts, so they should only be used in authorized environments.

## Hands-On Learning Path

Nmap proficiency is built by scanning progressively more realistic targets — on infrastructure that's explicitly legal to test. Below is the progression most cybersecurity students and self-taught practitioners use to build reps. Checked items reflect scans actually completed in my own lab or against authorized public targets.

**Public, legal-to-scan targets**
-  `scanme.nmap.org` — Nmap's own official test target, safe for basic scan practice
- TryHackMe "Nmap" and "Nmap: The Basics" rooms — guided, scored scanning exercises
-  OverTheWire "Bandit" wargame — light recon practice as part of a broader CTF-style challenge

**Home lab (VirtualBox / isolated network)**
-  Basic host discovery scan across a private subnet (`192.168.1.0/24`)
-  Service and version enumeration against a Metasploitable2 VM
-  Aggressive scan (`-A`) combining OS detection, version detection, NSE, and traceroute
-  Comparing SYN scan vs. Connect scan output/timing on the same target
-  Writing a custom NSE-driven scan against a deliberately outdated service to confirm a known CVE

**Applied / integration practice**
-  Feeding Nmap XML output (`-oX`) into a parsing script to automate reporting
-  Cross-referencing an Nmap scan against Wireshark capture of the same scan, to see both sides of the traffic



## Tips & Best Practices

- Always get explicit permission before scanning any network you do not own.
- Start with lighter scans before running aggressive ones.
- Use -oX (XML output) when integrating with other tools.
- Combine Nmap with tools like Nessus/OpenVAS for deeper vulnerability analysis.
- Get explicit authorization first. Never scan a network or host you don't own or don't have written permission to test — unauthorized scanning can violate policy or law even when no harm is intended.
- Match the scan to the goal. Use lighter, targeted scans (`-sV` on specific ports) when you know what you're looking for; reserve `-A` and full-range scans for situations where broad discovery is actually needed.
- Consider timing and noise. Faster timing templates (`-T4`/`-T5`) increase detection risk and can affect network performance — default to a more conservative template on production or shared networks.
- Always log your output. Save scans in multiple formats (`-oN`, `-oX`) so results can be reviewed, diffed against future scans, or fed into other tools.
- Verify findings before acting on them. Nmap's OS/version detection is a best-guess based on fingerprinting — confirm anything critical before making a security decision based on it.


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

Note: All IP addresses have been changed for privacy reasons.







