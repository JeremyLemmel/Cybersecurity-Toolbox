# theHarvester - OSINT Tool

**Category:** Open Source Intelligence (OSINT)  
**Difficulty:** Beginner  

## Description

theHarvester is a simple but powerful tool for gathering email addresses, subdomains, hostnames, and employee names from public sources using passive reconnaissance.

## Key Features
- Searches Google, Bing, LinkedIn, Twitter, etc.
- DNS brute forcing
- SSL/TLS certificate harvesting
- Can export results in multiple formats

## Hands-on Examples
#### Example 1: Recon on a Domain
- Ran theHarvester against a test domain to gather emails and subdomains.
- (Insert screenshot: theHarvester showing discovered emails and hosts)
#### Example 2: Exporting Results
- Exported findings to an HTML report for easier review.
- (Insert screenshot: HTML output example)

## What I Learned
- A surprising amount of information is publicly available.
- Importance of minimizing your digital footprint.
- Passive reconnaissance is a key first step in any pentest.

## Resources
- Official GitHub Repository
- OSINT Framework



## Common Commands

```bash
# Basic search
theHarvester -d example.com -b google

# Search multiple sources
theHarvester -d tesla.com -b google,bing,linkedin

# Limit results and save to file
theHarvester -d example.com -b all -l 500 -f results.html
