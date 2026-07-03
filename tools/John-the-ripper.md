# John the Ripper - Password Cracker

**Category:** Password Cracking & Hash Recovery  
**Difficulty:** Beginner to Intermediate  

## Description

John the Ripper (often called **John**) is one of the most popular open-source password cracking tools. It is used to detect weak passwords by cracking password hashes.

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

## Resources
- Official John the Ripper Documentation
- Hashcat vs John Comparison (both are useful)



## Common Commands

```bash
# Basic usage - crack a hash file
john hashes.txt

# Show cracked passwords
john --show hashes.txt

# Use a wordlist (most common method)
john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt

# Specify hash format
john --format=NT hashes.txt

# Brute force with rules
john --wordlist=wordlist.txt --rules hashes.txt
