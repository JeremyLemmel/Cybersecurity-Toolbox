# SQLMap - Automatic SQL Injection Tool

**Category:** Web Vulnerability Exploitation  
**Difficulty:** Intermediate  

## Description

SQLMap is an open-source tool that automates the detection and exploitation of SQL injection vulnerabilities.

Security professionals use sqlmap daily for:

- Confirming and exploiting suspected SQL injection points found during manual testing
- Enumerating database contents during authorized penetration tests
- Demonstrating real business impact beyond a simple "this parameter is vulnerable" finding
- Validating whether application-layer input sanitization actually holds up

## Key Features

- Automatic detection of boolean-based, time-based, error-based, and UNION-based SQL injection
- Database fingerprinting and enumeration (databases, tables, columns, data)
- Support for MySQL, PostgreSQL, MSSQL, Oracle, SQLite, and more
- Optional OS-level command execution (`--os-shell`) on supported configurations
- Tamper scripts to evade basic WAF/filter protections
- Direct integration with captured HTTP requests (e.g., from Burp Suite)


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

## Hands-On Learning Path

sqlmap proficiency comes from first understanding SQL injection manually, then learning what the tool automates — not the reverse. Below is the progression most cybersecurity students use to build reps.

**Guided / official starting points**
-  PortSwigger Web Security Academy SQL injection labs — solved manually first
-  TryHackMe SQL injection rooms

**Home lab (VirtualBox / isolated network)**
-  DVWA/OWASP Juice Shop SQLi challenges at increasing difficulty levels, comparing manual exploitation vs. sqlmap automation
-  Capturing a vulnerable request in Burp Suite and feeding it into sqlmap via `-r`, linking the two tools into one workflow
-  Testing the same injection point at default settings vs. increased `--risk`/`--level`, to see what additional depth actually reveals

**Applied / integration practice**
-  Documenting a full SQLi finding the way it would appear in a real pentest report: how it was found manually, how sqlmap confirmed/extended it, and business impact
-  Practicing recognizing when a WAF or filter is interfering, and understanding (without necessarily deploying) what tamper scripts are designed to address

## Best Practices

- **Authorization is non-negotiable.** sqlmap is an active exploitation tool, not a passive scanner — running it against a target without written permission is a serious legal risk.
- **Understand the query before automating it.** Confirm an injection point manually first; don't point sqlmap at a target blind.
- **Start conservative.** Default risk/level settings are safer; escalate (`--risk`, `--level`) deliberately and only when needed.
- **Treat `--os-shell` and `--os-cmd` as full compromise, not a "feature."** These can grant OS-level access — use only within explicit engagement scope.
- **Never run against production** without a controlled test environment or an explicit, documented change window.

## Resources
- Official SQLMap GitHub https://github.com/sqlmapproject/sqlmap
- SQLMap Wiki & User Manual https://github.com/sqlmapproject/sqlmap/wiki/Usage
- OWASP SQL Injection Prevention Cheat Sheet https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html


## Common Commands

### Enumeration

```bash
# Enumerate databases from a suspected injectable parameter
sqlmap -u "http://example.com/page?id=1" --dbs

# Enumerate tables within a specific database
sqlmap -u "http://example.com/page?id=1" -D dbname --tables

# Dump data from a specific table
sqlmap -u "http://example.com/page?id=1" -D dbname -T tablename --dump
```

### Working from Captured Requests

```bash
# Test using a request captured from Burp Suite
sqlmap -r request.txt --batch
```

### Adjusting Test Depth

```bash
# Increase test depth/risk (use cautiously — more intrusive and detectable)
sqlmap -u "http://example.com/page?id=1" --risk=3 --level=5
