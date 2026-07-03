# Autopsy - Digital Forensics Platform

**Category:** Digital Forensics & Incident Response  
**Difficulty:** Intermediate  

## Description

Autopsy is a free, open-source digital forensics platform built on The Sleuth Kit. It is used to analyze hard drives, mobile devices, and disk images.

Security professionals use Autopsy daily for:

- Post-incident forensic analysis of compromised systems
- Recovering deleted or hidden files as part of an investigation
- Building a timeline of file system activity to reconstruct what happened and when
- Supporting HR, legal, or law enforcement investigations that require a documented chain of custody

## Key Features
- Disk image analysis (E01, raw/dd, and other common forensic image formats)
- File recovery and carving — reconstructing deleted files
- Timeline analysis across file system metadata
- Keyword search and indexing across an entire image
- Hash filtering against known-good/known-bad hash sets (e.g., NSRL)
- Web artifact analysis (browser history, cookies, downloads)
- Windows registry analysis
- Modular ingest architecture — plugins extend analysis capability
- Case-based workflow with reporting output



## Hands-on Examples

**Example 1: Analyzing a Disk Image**  
- Processed a sample forensic image and recovered deleted files.
- *(Insert screenshot: Autopsy interface showing file system tree)*

**Example 2: Keyword Search & Timeline**  
- Found relevant artifacts using keyword search and timeline analysis.
- *(Insert screenshot: Autopsy timeline or keyword hit)*

## What I Learned
- Deleted files can often still be recovered.
- Understanding file systems is crucial for effective forensics.
- Chain of custody and proper documentation are essential in real investigations.

## Hands-On Learning Path

Forensic analysis proficiency comes from working through realistic, purpose-built disk images — never real personal or organizational data without explicit authorization. Below is the progression most cybersecurity students use to build reps.

**Guided / official starting points**
-  Autopsy's official tutorials and documentation walkthroughs
-  NIST CFReDS (Computer Forensic Reference Data Sets) — free, purpose-built practice images
-  Digital Corpora sample disk images
-  TryHackMe DFIR-focused rooms (e.g., "Autopsy")

**Home lab (practice images)**
-  Creating a case and importing a downloaded sample disk image
-  Recovering a deliberately deleted file from a test image
-  Building a file system activity timeline for a scenario image
-  Running a keyword search across an image for specific indicators (e.g., a known filename or string)

**Applied / integration practice**
-  Correlating Autopsy findings with network evidence from a Wireshark capture of the same simulated incident
-  Writing a full forensic report: chain-of-custody notes, methodology, findings, and how they'd feed into an incident response playbook



## Best Practices

- **Never work on original evidence.** Always analyze a verified forensic image or write-blocked copy — never the source media itself.
- **Maintain chain of custody.** Document who accessed evidence, when, and what was done — this is a legal requirement in many contexts, not just good practice.
- **Verify image integrity with hashing.** Compute and record MD5/SHA1 hashes before and after acquisition to prove the image wasn't altered.
- **Use write blockers during acquisition.** Physical or software write-blockers prevent accidental modification of source media.
- **Document methodology, not just findings.** A forensic report needs to be reproducible — someone else should be able to follow your steps and reach the same conclusion.
- **Corroborate before concluding.** A single artifact rarely tells the whole story — cross-reference multiple data points before drawing a conclusion.

## Resources
- Official Autopsy Website & Documentation https://www.autopsy.com/support/
- Digital Forensics with Autopsy tutorials https://digitalcorpora.org/

## Common Workflow
Autopsy is primarily GUI-driven. Its underlying engine, The Sleuth Kit, also provides CLI tools useful for scripting or quick lookups.

### Typical Case Workflow (GUI)

```
1. Create a new Case
2. Add a Data Source (disk image, local drive, or logical files)
3. Select ingest modules to run (hash lookup, keyword search, timeline, etc.)
4. Review results by category: File Types, Deleted Files, Timeline, Keyword Hits
5. Tag evidence and generate a report
```

### Sleuth Kit CLI (underlying engine)

```bash
# View partition layout of a disk image
mmls image.dd

# List all files recursively, including deleted ones
fls -r image.dd

# Extract a file by inode number
icat image.dd <inode> > recovered_file

# Display file system details
fsstat image.dd
