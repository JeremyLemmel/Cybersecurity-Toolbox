# Metasploit Framework Cheat Sheet

**Exploitation & Post-Exploitation**

### Core Commands
| Command | Description |
|---------|-----------|
| `search keyword` | Search modules |
| `use exploit/path` | Load module |
| `show options` | View settings |
| `set OPTION value` | Configure |
| `exploit` or `run` | Launch |

### Meterpreter Commands
| Command | Description |
|---------|-----------|
| `sysinfo` | System details |
| `getuid` | Current user |
| `shell` | Drop to system shell |
| `hashdump` | Dump password hashes |
| `screenshot` | Capture screen |
| `upload / download` | File transfer |
| `keyscan_start` | Start keylogger |

**Pro Tips**:
- Use `background` to return to msfconsole while keeping sessions alive.
- Always update Metasploit regularly (`msfupdate`).
- Test everything in an isolated lab environment.
