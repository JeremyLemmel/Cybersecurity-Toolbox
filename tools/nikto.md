# Nikto - Web Server Scanner

**Category:** Web Server & Vulnerability Scanning  
**Difficulty:** Beginner  

## Description

Nikto is an open-source web server scanner that tests for dangerous files, outdated software, and common misconfigurations on web servers.

Security professionals use Nikto daily for:

- Quick misconfiguration and outdated-software checks at the start of an assessment
- Establishing an initial risk baseline before investing time in manual testing
- Identifying dangerous or forgotten files/CGIs left exposed on a web server
- Validating that basic server hardening (headers, banners, default files) has actually been done

## Key Features
- 6,700+ checks for dangerous files, CGIs, and known vulnerabilities
- Outdated server software/version detection
- SSL/TLS support
- Tunable test categories (`-Tuning`) to scope a scan to specific check types
- Multiple output formats (txt, HTML, XML, CSV)
- Proxy support — can route scans through Burp Suite for deeper inspection of the traffic it generates

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

## Hands-On Learning Path

Nikto proficiency comes from learning to separate real findings from the noise it generates — the tool is intentionally broad, not precise. Below is the progression most cybersecurity students use to build reps.

**Guided / official starting points**
-  TryHackMe "Nikto" room
-  Running a scan against OWASP Juice Shop as a first-pass reconnaissance step

**Home lab (VirtualBox / isolated network)**
-  Scanning DVWA at different security levels and comparing what Nikto flags at each
-  Routing a Nikto scan through Burp Suite's proxy to see the full request/response traffic it generates
-  Comparing Nikto's automated findings against manual testing of the same target with Burp or ZAP

**Applied / integration practice**
-  Using Nikto as the first step in a layered workflow: Nikto → manual verification → deeper testing with Burp/ZAP
-  Documenting which Nikto findings were true positives vs. false positives after manual review


## Resources
- Official Nikto GitHub https://github.com/sullo/nikto
- OWASP Testing Guide https://owasp.org/www-project-juice-shop/



## Common Commands

### Basic Scans

```bash
# Basic scan against a host
nikto -h example.com

# Scan specific ports
nikto -h example.com -p 80,443

# Scan over SSL/TLS
nikto -h https://example.com -ssl
```

### Scoping and Tuning

```bash
# Limit scan to specific test categories (e.g., 1=file retrieval, 2=misconfig)
nikto -h example.com -Tuning 1,2,3
```

### Output and Integration

```bash
# Save output to a formatted report
nikto -h example.com -o report.html -Format html

# Route scan traffic through Burp Suite for inspection
nikto -h example.com -useproxy http://127.0.0.1:8080
```
