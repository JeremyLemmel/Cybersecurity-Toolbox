# Burp Suite Community Cheat Sheet

**Web Application Security Testing**

### Core Workflow
1. Configure browser proxy (127.0.0.1:8080)
2. Turn **Intercept** on/off
3. Browse the target application
4. Send requests to **Repeater** for manual editing
5. Use **Intruder** for automation

### Key Tools
| Tool | Best For |
|------|---------|
| **Proxy** | Intercepting & modifying traffic |
| **Repeater** | Manual payload testing |
| **Intruder** | Brute force, fuzzing, enumeration |
| **Comparer** | Comparing responses |
| **Decoder** | Encoding/decoding data |
| **Sequencer** | Session token randomness |

**Common Use Cases**:
- Authorization bypass testing
- SQL Injection / XSS testing
- Parameter tampering
- Session hijacking attempts

**Pro Tips**:
- Always define a Target Scope
- Use "Match and Replace" rules for automation
- Community edition has rate limits on Intruder
