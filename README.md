# windows-recycle-bin-artifact-investigation-dfir-lab
## Overview

Windows stores deleted files inside the Recycle Bin using two complementary forensic artifacts:

- **$I files** – Metadata describing the deleted file
- **$R files** – Actual contents of the deleted file

This lab demonstrates how investigators can analyze Recycle Bin artifacts to reconstruct deletion events, recover deleted files, and correlate metadata with recovered evidence during a Windows DFIR investigation.

---

# Executive Summary

A controlled DFIR investigation was conducted to understand how Windows stores deleted files within the Recycle Bin. Multiple files were created, deleted, and examined through PowerShell and Windows Explorer. The investigation successfully identified:

- Deleted file metadata
- Original file locations
- Deleted filenames
- Recoverable file contents
- Relationship between $I and $R artifacts

The exercise demonstrates one of the most common forensic artifact locations encountered during Windows endpoint investigations.

---

# Investigation Objectives

- Understand Windows Recycle Bin artifact structure
- Locate the Recycle Bin SID directory
- Examine $I metadata files
- Examine $R recovered files
- Recover deleted file contents
- Correlate metadata with recovered files
- Document forensic findings

---

# Skills Demonstrated

- Windows DFIR
- Deleted File Analysis
- Registry & File System Forensics
- Windows Artifact Analysis
- PowerShell Investigation
- Hidden System File Analysis
- Evidence Correlation
- Metadata Analysis
- Incident Documentation
- Timeline Reconstruction
- Digital Evidence Preservation

---

# Tools Used

- Windows 10 VM
- Windows Explorer
- PowerShell
- File Explorer
- Hidden System File Viewer

---

# Lab Environment

| Component | Details |
|----------|---------|
| Host OS | Windows 11 |
| Guest OS | Windows 10 x64 |
| Virtualization | VMware Workstation Player |
| Investigation Type | Host-Based DFIR |
| Evidence Source | Windows Recycle Bin |
| Artifact Type | $I / $R Files |

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1070.004 | File Deletion |
| T1005 | Data from Local System |
| T1083 | File and Directory Discovery |

Although this is a forensic investigation rather than an attack simulation, the analyzed artifacts commonly appear during investigations involving attacker cleanup and file deletion.

---

# Investigation Workflow

1. Create investigation folder structure
2. Create sample files
3. Delete selected files
4. Locate Recycle Bin
5. Access SID folder
6. Identify $I files
7. Identify $R files
8. Examine metadata
9. Recover deleted contents
10. Correlate evidence
11. Document findings

---

# Evidence Collected

- Recycle Bin screenshots
- Deleted files
- $I metadata files
- $R recovery files
- Original file paths
- Deletion timestamps
- PowerShell outputs

---

# Evidence Correlation

| Artifact | Evidence |
|----------|----------|
| $I File | Original filename, original location, deletion metadata |
| $R File | Recoverable deleted file contents |
| SID Folder | User-specific deleted file storage |
| PowerShell Output | Verification of artifact presence |
| Windows Explorer | Visual confirmation of deleted items |

---

# Investigation Findings

The investigation confirmed that Windows creates paired forensic artifacts whenever files are deleted into the Recycle Bin.

- $I files preserve metadata
- $R files preserve recoverable content
- Both artifacts remain available until the Recycle Bin is emptied
- Metadata and recovered content can be correlated to reconstruct user activity

---

# Key Takeaway

Windows Recycle Bin artifacts provide investigators with valuable evidence about deleted files, including metadata, original locations, deletion events, and recoverable file contents. Together, the $I and $R files enable accurate reconstruction of user deletion activity during DFIR investigations.
