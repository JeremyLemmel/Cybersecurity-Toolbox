# Nikto Cheat Sheet - Web Server Scanner

**Fast Web Server Vulnerability Scanner**

### Basic Commands
| Command | Description |
|---------|-----------|
| `nikto -h http://target.com` | Basic scan |
| `nikto -h https://target.com` | HTTPS target |
| `nikto -h target.com -p 8080` | Custom port |
| `nikto -h target.com -o report.html` | HTML report |
| `nikto -h target.com -Format csv` | CSV output |

### Useful Options
- `-Tuning x` → Scan tuning (1–9)
- `-evasion 1` → Random URI encoding
- `-Display V` → Verbose output
- `-maxtime 30m` → Maximum scan time

**Common Scan Tuning**:
- `1` = File Upload
- `2` = Misconfigurations
- `3` = Injection flaws
- `6` = Denial of Service
- `9` = Remote File Retrieval

**Pro Tips**:
- Nikto is noisy — use with caution on production systems.
- Always follow up with manual verification.
- Best used early in web app assessments.
