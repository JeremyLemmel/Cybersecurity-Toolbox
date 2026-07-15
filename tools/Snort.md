
### **Snort**
**Category:** Network Intrusion Detection System (IDS)  
**Difficulty:** Intermediate  

## Description
Snort is a free, open-source Network Intrusion Detection System (NIDS) and Intrusion Prevention System (IPS). It monitors network traffic in real-time and generates alerts based on predefined rules.

Security professionals use Snort for:
- Real-time network monitoring and threat detection
- Testing and validating attack tools
- Learning defensive security and rule writing
- Deploying as a lightweight IDS in labs and small environments

## Core Capabilities
- **Signature-based detection** using rules
- **Real-time packet inspection**
- **Custom rule creation**
- **Logging and alerting**

## Common Workflow
1. Configure Snort and enable community rules
2. Run Snort in IDS mode on a network interface
3. Generate attack traffic from Kali
4. Analyze alerts and logs

## Example Usage
**Example 1: Basic IDS Monitoring**  
- Configured Snort on Kali Linux and monitored network traffic in real time.

**Example 2: Detecting Network Scanning**  
- Ran Snort while performing a network scan using Angry IP Scanner from Windows Server 2022. Successfully detected scanning activity.

**Example 3: Alert Analysis**  
- Stopped Snort after scanning activity and analyzed Packet Statistics, Module Statistics, and AppID Statistics to understand detected traffic.

## What I Learned
- How intrusion detection systems work in practice
- The importance of proper rule tuning to reduce false positives
- The perspective of defensive security when being attacked
- Differences between detection and prevention

## Hands-On Learning Path
- Configured NAT networking between Windows Server 2022 and Kali Linux
- Installed and ran Snort in IDS mode
- Simulated network scanning with Angry IP Scanner
- Analyzed Snort output and statistics

## Resources
- Snort Official Documentation: https://www.snort.org/documents
- Snort Community Ruleset
