# OpenVAS / Greenbone Cheat Sheet

**Vulnerability Management Scanner**

### Basic Workflow
1. Start Greenbone services (`sudo gvm-start`)
2. Log into Greenbone Security Assistant (https://127.0.0.1:9392)
3. Create a new **Scan Config**
4. Create a **Target**
5. Create and start a **Task**

### Key Features
- Authenticated scanning (credentialed)
- Unauthenticated scanning
- CVE-based vulnerability detection
- Compliance checking
- Detailed remediation suggestions

**Best Practices**:
- Use credentialed scans when possible (much more accurate)
- Schedule regular scans
- Export reports in PDF/HTML
- Review high/critical findings first

**Pro Tips**:
- Update feed regularly (`greenbone-feed-sync`)
- Use host discovery scan first
- Combine with manual testing for best results
