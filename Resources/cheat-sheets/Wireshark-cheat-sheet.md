# Wireshark Cheat Sheet - Packet Analysis

**Network Traffic Analysis & Troubleshooting**

### Essential Display Filters
| Filter | Purpose |
|--------|--------|
| `http` | All HTTP traffic |
| `dns` | DNS queries and responses |
| `tls.handshake` | TLS/SSL handshake |
| `tcp.port == 80 or tcp.port == 443` | Web traffic |
| `ip.addr == 192.168.1.100` | Filter by IP |
| `http.request.method == "POST"` | POST requests only |
| `frame contains "password"` | Search for keywords |

### Analysis Techniques
- **Follow Stream** → TCP / UDP / TLS
- **Statistics → Conversations** → Top talkers
- **Statistics → IO Graph** → Bandwidth usage over time
- **Statistics → Protocol Hierarchy** → Breakdown by protocol
- **File → Export Objects** → Extract images, files, etc.

**Pro Tips**:
- Color rules help quickly identify suspicious traffic.
- Use `&&` (AND) and `||` (OR) to combine filters.
- Right-click packet → Follow → TCP Stream is extremely useful.
