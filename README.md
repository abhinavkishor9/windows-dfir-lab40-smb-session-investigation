# windows-dfir-lab40-smb-session-investigation

## Overview

The Server Message Block (SMB) protocol enables Windows systems to share files, folders, and printers across a network. During Digital Forensics and Incident Response (DFIR), investigators analyze SMB artifacts to determine who accessed shared resources, when connections were established, and what files were available over the network.

In this hands-on DFIR lab, a Windows shared folder was created using native PowerShell commands. The investigation focused on creating and validating SMB shares, examining SMB server configuration, understanding SMB session artifacts, and documenting observations using built-in Windows tools.

---

# Executive Summary

This investigation demonstrates how Windows SMB shares can be created and analyzed using native PowerShell without requiring third-party forensic software. The workflow covered SMB share creation, validation, server configuration review, and an introduction to SMB session analysis.

Although localhost access may not generate active SMB session records on every Windows edition, the lab demonstrates the commands and investigative methodology used during enterprise DFIR investigations.

---

# Investigation Objectives

- Understand the SMB protocol.
- Create a Windows SMB share.
- Enumerate available SMB shares.
- Examine SMB server configuration.
- Attempt to identify active SMB sessions.
- Review open SMB files.
- Correlate investigation findings.
- Document forensic observations.

---

# Skills Demonstrated

- Windows SMB Investigation
- Windows DFIR Methodology
- Host-Based Forensic Investigation
- PowerShell Administration
- SMB Share Enumeration
- SMB Configuration Analysis
- Evidence Correlation
- Investigation Documentation
- Incident Reporting

---

# Tools Used

- Windows 10
- Windows PowerShell
- File Explorer

---

# Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Windows 10 |
| Investigation Type | Host-Based DFIR |
| Analysis Method | Native Windows Tools |
| Primary Artifact | Windows SMB Shares |
| Shell | Windows PowerShell |
| Privileges | Administrator |

---

# Investigation Workflow

1. Create investigation workspace.
2. Create sample files.
3. Create SMB share.
4. Verify SMB share.
5. Access shared folder.
6. Review SMB sessions.
7. Review open SMB files.
8. Examine SMB server configuration.
9. Correlate findings.
10. Remove lab artifacts.

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1021.002 | SMB/Windows Admin Shares |
| T1039 | Data from Network Shared Drive |
| T1083 | File and Directory Discovery |

---

# Evidence Collected

- SMB share configuration
- Sample shared files
- PowerShell outputs
- SMB server configuration
- Share enumeration
- Session enumeration results
- Cleanup validation

---

# Evidence Correlation

The investigation correlated SMB share configuration with PowerShell enumeration to verify successful share creation. Native Windows commands were used to review SMB sessions, open files, and server configuration. Localhost testing demonstrated the investigative workflow while highlighting that active SMB session artifacts may not always be generated during local testing.

---

# Investigation Findings

The investigation confirmed successful SMB share creation and enumeration using PowerShell. SMB server configuration was successfully reviewed, and the lab demonstrated the commands used to investigate SMB sessions and open files. Although localhost connections did not generate active session artifacts in this environment, the investigation reflected the same methodology used during enterprise DFIR investigations.

---

# Key Takeaway

Windows SMB artifacts provide valuable evidence during incident response by revealing shared resources, connected users, and network file access. Understanding how to enumerate SMB shares, inspect server configuration, and review session information prepares analysts for investigating lateral movement and file-sharing activity in enterprise environments.
