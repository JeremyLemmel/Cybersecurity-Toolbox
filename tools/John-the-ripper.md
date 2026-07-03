# John the Ripper - Password Cracker

**Category:** Password Cracking & Hash Recovery  
**Difficulty:** Beginner to Intermediate  

## Description

John the Ripper (often called **John**) is one of the most popular open-source password cracking tools. It is used to detect weak passwords by cracking password hashes.

Security professionals use John the Ripper daily for:

- Auditing password strength during authorized penetration tests
- Testing whether an organization's password policy actually holds up against real cracking techniques
- Recovering credentials during authorized red team or forensic engagements
- Demonstrating to non-technical stakeholders why "password123" is a real risk, not a hypothetical one

## Key Features
- Supports hundreds of hash types
- Automatic detection of hash format
- Wordlist + brute-force + mask attacks
- Incremental mode (smart brute force)
- Ability to resume cracked sessions

## Hands-on Examples
#### Example 1: Cracking NTLM Hashes
- Cracked Windows NTLM password hashes using a wordlist.
- (Insert screenshot: John the Ripper cracking hashes with progress)
#### Example 2: Using RockYou Wordlist
- Used the famous rockyou.txt wordlist against a hash file.
- (Insert screenshot: John --show output displaying cracked passwords)

## What I Learned
- Most real-world passwords are cracked using wordlists + rules rather than pure brute force.
- The importance of using strong, unique passwords and password managers.
- Hash types matter — using the wrong format wastes time.

## Hands-On Learning Path

Password cracking proficiency comes from working with real hash formats under realistic constraints — on data you're explicitly authorized to test. Below is the progression most cybersecurity students and self-taught practitioners use to build reps.

**Guided / CTF platforms**
-  TryHackMe "Crack the Hash" — identifying hash types and cracking them, from easy to advanced
-  TryHackMe "John the Ripper: The Basics" room
-  HackTheBox easy-rated machines that require cracking an extracted hash as part of the path

**Concept-building exercises**
-  Identifying hash types manually (length, format, prefix) before letting John auto-detect, to build pattern recognition
-  Cracking a `/etc/shadow` dump from a personal VM using `unshadow` + `rockyou.txt`
-  Comparing crack time for the same password hashed with MD5 vs. bcrypt, to see algorithm strength in practice
-  Writing a custom mangling rule and measuring its impact on crack rate vs. the default rule set

**Applied / integration practice**
-  Extracting hashes from a Windows SAM database in an isolated lab VM and cracking with the appropriate format
-  Documenting a full password-audit workflow: extract → identify format → crack → report strength findings

## Best Practices

- **Only crack hashes you're explicitly authorized to test.** Password cracking against systems or accounts without permission is illegal in most jurisdictions, regardless of intent.
- **Never reuse or act on recovered credentials beyond the scope of the engagement.** A password recovered during a test is not a general-purpose access credential.
- **Match the attack to the target.** Try wordlists and rules before brute force — incremental mode against strong hashing algorithms can take longer than any engagement window allows.
- **Understand hash algorithm strength, not just the tool.** A fast crack against MD5 says nothing about how a properly salted bcrypt hash will behave — know the difference before drawing conclusions.
- **Document methodology, not just results.** A password audit report showing *how* weak passwords were found (technique, wordlist, time-to-crack) is more useful to an organization than a plaintext list alone.



## Resources
- Official John the Ripper Documentation https://www.openwall.com/john/doc/
- Hashcat vs John Comparison (both are useful)
- John the Ripper "Jumbo" GitHub Repository https://github.com/openwall/john



## Common Commands

### Basic Cracking

```bash
# Crack a hash file using John's default wordlist and rules
john hashes.txt

# Crack using a specific wordlist
john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt

# Show already-cracked passwords from a hash file
john --show hashes.txt
```

### Specifying Hash Format

```bash
# Force a specific hash format (useful when auto-detection is ambiguous)
john --format=NT hashes.txt
john --format=sha512crypt hashes.txt
```

### Preparing Linux Password Files

```bash
# Combine /etc/passwd and /etc/shadow into a crackable format
unshadow /etc/passwd /etc/shadow > combined.txt
john combined.txt
```

### Rule-Based and Incremental Attacks

```bash
# Apply mangling rules to a wordlist (e.g., leetspeak substitutions, appended numbers)
john --wordlist=rockyou.txt --rules hashes.txt

# Brute-force mode (tries all character combinations — slow, last resort)
john --incremental hashes.txt
```
