
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
- Configured Snort and successfully detected Nmap scans and Metasploit activity.

**Example 2: Custom Rule Creation**  
- Wrote and tested custom Snort rules to detect specific attack patterns.

**Example 3: Alert Analysis**  
- Generated malicious traffic and analyzed Snort’s real-time alerts and log files.

## What I Learned
- How intrusion detection systems work in practice
- The importance of proper rule tuning to reduce false positives
- The perspective of defensive security when being attacked
- Differences between detection and prevention

## Hands-On Learning Path
- Running Snort while performing scans and exploits against Metasploitable
- Writing custom rules for common attacks (Nmap, brute force, etc.)
- Comparing default rules vs custom rules

## Resources
- Snort Official Documentation: https://www.snort.org/documents
- Snort Community Ruleset
