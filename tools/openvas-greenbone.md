# OpenVAS / Greenbone - Vulnerability Scanner

**Category:** Vulnerability Management  
**Difficulty:** Intermediate  

## Description

OpenVAS (now part of **Greenbone Vulnerability Management**) is a powerful open-source vulnerability scanner. It is one of the best free alternatives to Nessus.

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

## Resources
- Greenbone Official Documentation
- OpenVAS / GVM GitHub



## Setup & Common Usage

```bash
# Start Greenbone services (Kali)
sudo gvm-start

# Access via browser at https://127.0.0.1:9392
