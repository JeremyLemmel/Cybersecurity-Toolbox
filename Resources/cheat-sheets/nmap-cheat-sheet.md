# Nmap Cheat Sheet

**Quick Reference for Network Scanning**

## Core Workflow

1. Host discovery (is it alive?)
2. Port scan (what's open?)
3. Service/version detection (what's running?)
4. NSE scripts (any known issues?)
5. Save output for reporting



## Basic Commands

| Command | Description |
|---------|-----------|
| `nmap 192.168.1.1` | Scan a single IP |
| `nmap 192.168.1.1-255` | Scan a range |
| `nmap 192.168.1.0/24` | Scan a subnet |
| `nmap scanme.nmap.org` | Scan a hostname |

## Most Useful Scan Types

| Option | Command | Purpose |
|--------|--------|--------|
| Basic Scan | `nmap target.com` | Default TCP scan |
| Service Version | `nmap -sV target.com` | Detect service versions |
| Aggressive | `nmap -A target.com` | OS, version, scripts + traceroute |
| Stealth SYN | `sudo nmap -sS target.com` | Half-open stealth scan |
| UDP Scan | `sudo nmap -sU target.com` | Scan UDP ports |
| All Ports | `nmap -p- target.com` | Scan all 65,535 ports |

## Common Port Specifications

| Command | Description |
|---------|-----------|
| `-p 80,443` | Scan specific ports |
| `-p 1-1000` | Scan first 1000 ports |
| `-p-` | Scan all ports |
| `--top-ports 100` | Scan top 100 most common ports |

## Timing & Performance

| Option | Speed | Use Case |
|--------|-------|---------|
| `-T0` | Paranoid (very slow) | IDS evasion |
| `-T2` | Polite | Normal networks |
| `-T4` | Aggressive | Fast networks |
| `-T5` | Insane (very fast) | LAN / testing only |

## Output Options

| Command | Output Format |
|---------|-------------|
| `-oN scan.txt` | Normal text file |
| `-oX scan.xml` | XML format |
| `-oG scan.grep` | Grepable format |
| `-oA scan` | All three formats |

## Pro Tips
- Always use sudo for SYN scans (-sS), UDP scans, and OS detection.
- Use -oA when you want all output formats.
- Never scan networks without explicit permission.
- Combine Nmap with vulnerability scanners (OpenVAS) for best results.

## Useful Combinations

```bash
# Recommended general scan
nmap -sV -sC -O -T4 target.com

# Full detailed scan
nmap -A -T4 -p- target.com -oA fullscan

# Fast + version detection
nmap -sV --top-ports 1000 -T4 target.com



