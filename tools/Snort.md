
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

<img width="728" height="223" alt="Screenshot 2026-07-15 121638" src="https://github.com/user-attachments/assets/2ea6875f-436a-4db1-a73d-70fa46f65b84" />
<img width="781" height="345" alt="Screenshot 2026-07-15 121649" src="https://github.com/user-attachments/assets/d24f5a25-3e8c-4479-b477-d1506df7fa80" />
<img width="519" height="541" alt="Screenshot 2026-07-15 121700" src="https://github.com/user-attachments/assets/ce778bd7-82e1-43f3-923e-a45dc818a67a" />


  

**Example 2: Detecting Network Scanning**  
- Ran Snort while performing a network scan using Angry IP Scanner from Windows Server 2022. Successfully detected scanning activity.
<img width="799" height="522" alt="Screenshot 2026-07-15 121828" src="https://github.com/user-attachments/assets/a14d5da6-0cb1-438f-8e27-3aab4cfc8a55" />


**Example 3: Alert Analysis**  
- Stopped Snort after scanning activity and analyzed Packet Statistics, Module Statistics, and AppID Statistics to understand detected traffic.

<img width="509" height="498" alt="Screenshot 2026-07-15 121734" src="https://github.com/user-attachments/assets/c6f259e7-d737-4fef-9905-eb61cad74579" />
<img width="451" height="792" alt="Screenshot 2026-07-15 121803" src="https://github.com/user-attachments/assets/b97c876f-5a79-47e5-9c6a-2f5ab2c883b0" />



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
