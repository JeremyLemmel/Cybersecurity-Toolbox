# Wazuh - Open Source SIEM & XDR

**Category:** Security Information & Event Management (SIEM)  
**Difficulty:** Intermediate  

## Description

Wazuh is a free, open-source security platform that provides threat detection, incident response, and compliance capabilities. It is one of the best open-source SIEM solutions.

## Key Features
- Log analysis & correlation
- File integrity monitoring (FIM)
- Vulnerability detection
- Active response
- Agent-based and agentless monitoring

## Hands-on Examples
### Example 1: Deploying Wazuh Agent
- Installed and registered an agent on a Windows/Linux VM.
- (Insert screenshot: Wazuh dashboard showing connected agents)
### Example 2: Creating a Custom Alert Rule
- Set up a rule to detect failed login attempts.
- (Insert screenshot: Wazuh dashboard with security events or alerts)

## What I Learned
- Centralized log collection is extremely valuable for detection.
- Proper tuning of rules is needed to reduce alert fatigue.
- Wazuh is a production-grade SIEM that scales well.

## Resources
- Official Wazuh Documentation
- Wazuh GitHub Repository


## Basic Setup Commands (Kali)

```bash
# Quick single-node deployment (All-in-One)
curl -sO https://packages.wazuh.com/4.8/wazuh-install.sh && bash wazuh-install.sh -a
