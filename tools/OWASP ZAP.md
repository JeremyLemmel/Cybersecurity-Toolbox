# OWASP ZAP (Zed Attack Proxy)

**Category:** Web Application Security Scanner  
**Difficulty:** Beginner to Intermediate  

## Description

OWASP ZAP is a free, open-source web app security scanner and proxy maintained by OWASP. It is an excellent alternative/complement to Burp Suite.

Security professionals use OWASP ZAP daily for:

- Automated baseline security scans of web applications
- Manual testing via its intercepting proxy, similar to Burp Suite's core workflow
- Integrating security scanning directly into CI/CD pipelines
- Learning web application vulnerability classes in a free, fully-featured tool


## Key Features
- Automated spidering + active scanning
- Passive scanning
- AJAX Spider
- Fuzzer
- Report generation

## Walkthrough Examples
#### Example 1: Quick Scan on DVWA
- Ran a full scan against Damn Vulnerable Web Application and reviewed findings.
- (Insert screenshot: ZAP dashboard with alerts)
#### Example 2: Spidering a Site
- Used the spider to crawl and discover hidden pages.
#### Example 3: Generating a Report
- Exported HTML/PDF report with risk levels (High/Medium/Low).

## What I Learned
- Automated scanners are great for finding low-hanging fruit but still require manual verification
- Importance of setting proper scope to avoid scanning out of bounds

## Hands-On Learning Path

ZAP proficiency is built by scanning intentionally vulnerable applications before touching anything with real stakes. Below is the progression most cybersecurity students and self-taught practitioners use to build reps.

**Guided / official starting points**
-  OWASP's official "Zap in Ten" video tutorial series
-  Running a baseline scan against OWASP Juice Shop
-  TryHackMe "OWASP ZAP" room

**Home lab (VirtualBox / isolated network)**
-  Running a full active scan against DVWA at increasing security levels, and comparing findings
-  Using the intercepting proxy manually to modify a request, mirroring the Burp Suite Repeater workflow
-  Comparing ZAP's automated findings against manual testing of the same application, to see what automation catches and misses

**Applied / integration practice**
-  Setting up a ZAP baseline scan as a step in a personal CI/CD pipeline (e.g., GitHub Actions) against a test app
-  Triaging ZAP's automated alert output — separating true positives from noise, and documenting the reasoning

## Resources
- Official OWASP ZAP Website https://www.zaproxy.org/docs/
- ZAP HUD (Heads-Up Display) tutorial



## Common Usage

### Docker Quick-Start (Baseline Scan)

```bash
# Run a passive baseline scan against a target
docker run -t owasp/zap2docker-stable zap-baseline.py -t https://example.com
```

### Using zap-cli

```bash
# Start ZAP daemon
zap-cli start

# Spider a target to map its structure
zap-cli spider https://example.com

# Run an active scan (only against authorized targets)
zap-cli active-scan https://example.com

# Generate an HTML report of findings
zap-cli report -o report.html -f html
```

### Full Automated Scan (Docker)

```bash
# Passive + active scan combined, with a generated report
docker run -t owasp/zap2docker-stable zap-full-scan.py -t https://example.com -r report.html
```
