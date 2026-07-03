# Wazuh - Open Source SIEM & XDR

**Category:** Security Information & Event Management (SIEM)  
**Difficulty:** Intermediate  

## Description

Wazuh is a free, open-source security platform that provides threat detection, incident response, and compliance capabilities. It is one of the best open-source SIEM solutions.

Security professionals use Wazuh daily for:

- Centralized log correlation across an environment's endpoints
- Endpoint-level threat detection (file integrity, rootkits, malware indicators)
- Vulnerability detection tied to actual installed software inventory
- Compliance reporting against frameworks like PCI DSS, HIPAA, and GDPR

## Key Features
- Centralized log collection and analysis from agents across an environment
- File Integrity Monitoring (FIM) — alerts on unauthorized file/config changes
- Vulnerability detection — correlates installed software against known CVEs
- Active response — automated actions triggered by specific alerts
- Compliance monitoring modules (PCI DSS, HIPAA, GDPR, and others)
- Web-based dashboard (Wazuh Dashboard, built on OpenSearch/Kibana-style visualization)

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

## Hands-On Learning Path

Wazuh proficiency comes from building and tuning a real deployment, not just reading dashboards someone else configured. Below is the progression most cybersecurity students use to build reps.

**Guided / official starting points**
-  Following Wazuh's official Quickstart guide to stand up a single-node deployment
-  Completing Wazuh's free training modules to understand core architecture (manager, agents, indexer, dashboard)

**Home lab (VirtualBox / isolated network)**
-  Standing up a Wazuh manager + agent pair in a home lab
-  Triggering a File Integrity Monitoring alert by modifying a monitored file/directory
-  Running the vulnerability detection module against a deliberately unpatched lab VM
- Tuning a noisy default rule to reduce false positives, and documenting the before/after

**Applied / integration practice**
-  Comparing Wazuh's alert/detection workflow against the Splunk-based detection lab from my SOC capstone, to see how two SIEM approaches handle the same simulated event differently
-  Mapping a Wazuh alert rule to a corresponding MITRE ATT&CK technique, consistent with the framework used throughout the rest of this portfolio

## Best Practices

- **Secure the manager itself.** As the central point of visibility and control, a compromised Wazuh manager is a high-value target — harden it accordingly.
- **Tune rules deliberately.** Default rule sets generate significant noise — tuning is what turns Wazuh from "alert firehose" into something actually actionable.
- **Protect agent enrollment keys.** A leaked enrollment key could let an unauthorized host register as a trusted agent.
- **Keep the vulnerability feed current.** Detection quality depends directly on how up to date the underlying CVE data is.
- **Be conservative with active response.** Automated actions (e.g., auto-blocking an IP) can cause outages if misconfigured — test thoroughly before enabling in a live environment.

## Resources 
- Official Wazuh Documentation https://documentation.wazuh.com/
- Wazuh GitHub Repository https://github.com/wazuh/wazuh
- Wazuh Free Training & Certification https://wazuh.com/training/

## Basic Setup Commands (Kali)

### Agent Setup

```bash
# Install and register an agent (Debian-based, pointed at a manager)
WAZUH_MANAGER='10.0.0.5' apt-get install wazuh-agent

# Start/check agent status
systemctl start wazuh-agent
systemctl status wazuh-agent

# Manual agent registration to a manager
/var/ossec/bin/agent-auth -m 10.0.0.5
```

### Manager Management

```bash
# Check manager status
systemctl status wazuh-manager
/var/ossec/bin/wazuh-control status
