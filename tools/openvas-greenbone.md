# OpenVAS / Greenbone - Vulnerability Scanner

**Category:** Vulnerability Management  
**Difficulty:** Intermediate  

## Description

OpenVAS (now part of **Greenbone Vulnerability Management**) is a powerful open-source vulnerability scanner. It is one of the best free alternatives to Nessus.

Security professionals use OpenVAS daily for:

- Enterprise-scale vulnerability assessments across large host inventories
- Patch-prioritization support via CVSS-based severity scoring
- Recurring, scheduled scanning as part of a vulnerability management program
- Compliance-driven scanning requirements

## Key Features
- Regular vulnerability feed updates
- Authenticated and unauthenticated scanning
- Detailed reporting
- Web-based Greenbone Security Assistant (GSA) interface

## Hands-on Examples
### Example 1: Full Network Scan
- Performed a full vulnerability scan against a lab network.
- (Insert screenshot: Greenbone dashboard with scan task)
### Example 2: Scan Results Analysis
- Reviewed high and critical vulnerabilities with remediation suggestions.
- (Insert screenshot: Greenbone vulnerability report showing findings)

## What I Learned
- Authenticated scans provide much deeper and more accurate results.
- Interpreting scanner output requires human judgment.
- Vulnerability management is an ongoing process, not a one-time task.

## Hands-On Learning Path

OpenVAS proficiency comes from running real scans against known-vulnerable targets and learning to read a full report critically, not just running the default configuration. Below is the progression most cybersecurity students use to build reps.

**Guided / official starting points**
-  Installing Greenbone Community Edition following the official setup docs
-  Reviewing a sample scan report to understand CVSS scoring and severity breakdowns before running a first real scan

**Home lab (VirtualBox / isolated network)**
-  Running an unauthenticated scan against a Metasploitable2 VM
-  Running the same scan authenticated, to directly compare depth of findings
-  Cross-referencing OpenVAS's CVE findings against vulnerabilities manually confirmed via Nmap NSE scripts

**Applied / integration practice**
-  Practicing full report triage — sorting and prioritizing findings by CVSS score and exploitability
-  Scheduling a recurring scan and comparing results across two scan cycles to see how findings change after a simulated patch


## Resources
- Greenbone Official Documentation https://greenbone.github.io/docs/
- OpenVAS / GVM GitHub https://github.com/greenbone



## Setup & Common Usage

OpenVAS is primarily GUI-driven; CLI/API access is available via `gvm-cli`.

```bash
# Initial setup and service management
gvm-setup
gvm-start
gvm-check-setup
```

```
Typical scan workflow (via GUI):
1. Configure a Target (host/IP range, optional credentials)
2. Create a Task (target + scan config)
3. Run the Task
4. Review the Report, sorted by CVSS severity
```
