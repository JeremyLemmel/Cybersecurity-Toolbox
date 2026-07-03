# Nikto - Web Server Scanner

**Category:** Web Server & Vulnerability Scanning  
**Difficulty:** Beginner  

## Description

Nikto is an open-source web server scanner that tests for dangerous files, outdated software, and common misconfigurations on web servers.

## Key Features
- Scans for over 6,700 dangerous files/CGIs
- Checks for outdated server versions
- Looks for server configuration issues
- Plugin-based architecture

## Hands-on Examples
#### Example 1: Scanning a Test Server
- Scanned a vulnerable web server (DVWA) and reviewed findings.
- (Insert screenshot: Nikto scan in progress)
#### Example 2: HTML Report Output
- Generated and reviewed a professional HTML report.
- (Insert screenshot: Nikto HTML report showing vulnerabilities)

## What I Learned
- Many web servers have unnecessary files exposed.
- Regular vulnerability scanning is essential even for simple websites.
- Nikto is fast for initial reconnaissance but should be paired with manual testing.

## Resources
- Official Nikto GitHub
- OWASP Testing Guide



## Common Commands

```bash
# Basic scan
nikto -h http://example.com

# Scan with evasion techniques
nikto -h http://example.com -evasion 1

# Save output to file
nikto -h http://192.168.1.100 -o nikto-report.html
