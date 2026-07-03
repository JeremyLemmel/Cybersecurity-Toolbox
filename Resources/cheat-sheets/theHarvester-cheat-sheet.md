# theHarvester Cheat Sheet - OSINT Reconnaissance

**Passive Information Gathering Tool**

### Basic Commands
| Command | Description |
|---------|-----------|
| `theHarvester -d domain.com -b google` | Basic Google search |
| `theHarvester -d domain.com -b all` | Search all sources |
| `theHarvester -d domain.com -b linkedin,google,bing` | Multiple sources |
| `theHarvester -d domain.com -l 500` | Limit results |
| `theHarvester -d domain.com -f output.html` | Save to HTML file |

### Useful Options
- `-s` → Start result number (pagination)
- `-v` → Show virtual hosts
- `-e` → Use specific DNS server
- `-t` → Perform DNS TLD expansion

### Common Sources
`google, bing, baidu, linkedin, twitter, github, hunter, intelx`

**Pro Tips**:
- Use after initial domain enumeration.
- Great for finding employee emails and subdomains.
- Combine with Amass or Sublist3r for better results.
- Always respect rate limits to avoid being blocked.
