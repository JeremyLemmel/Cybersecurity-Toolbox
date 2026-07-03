# SQLMap - Automatic SQL Injection Tool

**Category:** Web Vulnerability Exploitation  
**Difficulty:** Intermediate  

## Description

SQLMap is an open-source tool that automates the detection and exploitation of SQL injection vulnerabilities.

## Key Features
- Detects various types of SQL injection
- Supports many database types (MySQL, PostgreSQL, MSSQL, etc.)
- Can dump databases, tables, and user credentials
- Powerful enumeration features

## Hands-on Examples
### Example 1: Testing DVWA
- Discovered and exploited a SQL injection vulnerability in Damn Vulnerable Web Application.
- (Insert screenshot: SQLMap detecting injection point)
### Example 2: Database Dumping
- Successfully extracted database tables and user credentials.
- (Insert screenshot: SQLMap dumping users table)

## What I Learned
- Input sanitization and prepared statements are critical defenses.
- Even simple SQL injection can lead to full database compromise.
- Automated tools are great, but manual verification is still necessary.

## Resources
- Official SQLMap GitHub
- SQLMap Wiki & User Manual



## Common Commands

```bash
# Basic scan
sqlmap -u "http://example.com/login.php?id=1"

# Auto detect and exploit
sqlmap -u "http://target.com/vuln.php?id=1" --batch --dump

# Specify database type
sqlmap -u URL --dbms=mysql --dump
