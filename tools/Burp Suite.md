# Burp Suite Community Edition

**Category:** Web Application Security Testing  
**Difficulty:** Intermediate  

## Description

Burp Suite is the leading toolkit for web application penetration testing. The Community edition is completely free and extremely powerful.

Security professionals use Burp Suite daily for:

- Manual web application penetration testing
- Finding logic flaws and injection points automated scanners miss
- Testing authentication and session management
- Understanding what real exploitation attempts look like at the HTTP request level

## Core Tools Used
- **Proxy** — intercepts and lets you inspect/modify HTTP(S) traffic in real time
- **Repeater** — resend a modified request repeatedly to test how the application responds
- **Intruder** — automate sending requests with varying payloads (e.g., for fuzzing or parameter testing)
- **Target/Scope** — defines what's in-bounds for testing to avoid touching out-of-scope systems
- **Decoder** — encode/decode data (Base64, URL encoding, hashing) found in requests
- **Extensions (BApp Store)** — add community-built tools for specialized testing

## Common Workflow

1. Configure browser proxy (127.0.0.1:8080)
2. Turn Intercept On/Off
3. Send requests to Repeater for manual testing
4. Use Intruder for fuzzing and brute forcing

## Example Usage

**Example 1: Intercepting and Modifying Requests**  
- Intercepted a login request and modified parameters.
- *(Insert screenshot: Burp Proxy intercepting a request)*

**Example 2: SQL Injection Testing**  
- Used Repeater to test different payloads.

**Example 3: Brute Force Attack**  
- Used Intruder with a wordlist against a login form (in lab only).

## What I Learned
- How modern web apps communicate behind the scenes
- The impact of improper input validation
- Difference between manual and automated testing

## Hands-On Learning Path

Burp Suite proficiency is built through repetition against intentionally vulnerable, legal-to-attack targets. Below is the progression most cybersecurity students and self-taught practitioners use — the same one I'm working through. Checked items reflect labs actually completed; this list updates as real work is done.

**PortSwigger Web Security Academy** *(free, built by the makers of Burp — the most widely used starting point)*
-  SQL injection — retrieving hidden data via a login bypass
-  Cross-site scripting (XSS) — reflected, stored, and DOM-based labs
-  Authentication — username enumeration and password brute-forcing with Intruder
-  Access control vulnerabilities — IDOR and privilege escalation labs
-  Cross-site request forgery (CSRF) — bypassing basic CSRF token validation
-  Business logic vulnerabilities — exploiting flawed application assumptions

**OWASP Juice Shop** *(intentionally vulnerable app, gamified with a scoreboard)*
-  Intercepting and modifying a request to manipulate a price or quantity
-  Identifying and exploiting a broken access control challenge
-  Using Repeater to test input validation on a form field

**DVWA (Damn Vulnerable Web Application)** *(classic, security-level-adjustable practice target)*
-  Low-security SQL injection via Burp's Repeater
-  Command injection testing at increasing security levels
-  Comparing how the same attack behaves at "low" vs. "high" security settings — a good way to see what real mitigations look like in practice

## Resources
- PortSwigger Web Security Academy (Free training)
- Burp Suite Documentation https://portswigger.net/burp/documentation
