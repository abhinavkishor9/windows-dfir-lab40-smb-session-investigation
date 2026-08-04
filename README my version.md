# windows-dfir-lab40-smb-session-investigation

## Overview

SMB (Server Message Block) is a Windows network protocol used for:

File sharing
Printer sharing
Accessing shared folders
Remote administration

Examples:

Accessing a shared folder on another computer
Mapping a network drive
Copying files over the network.

Whenever one computer connects to another computer's shared resource, Windows creates an SMB session.
The session records information such as:

Connected user
Client computer
Open time
Session status
Shared resources being accessed

Attackers frequently use SMB for:

Lateral movement
File theft
Malware deployment
Remote administration
Credential abuse

During investigations, analysts ask questions like:

Who connected?
From which IP address?
Which shared folder was accessed?
Is the connection still active?
When did the session start?

In this DFIR lab, a Windows shared folder was created using native PowerShell commands. We created and validated SMB shares and examined SMB server configuration.

---

# Executive Summary

This investigation shows how do we create SMB shares and analyzed using native PowerShell without requiring third-party forensic software. 
Suppose an employee reports that confidential files disappeared from a shared folder.

As a DFIR analyst, you need to determine:

Was someone connected to the server?
Which user established the connection?
Was the session still active?
Was it a legitimate user?

Windows maintains SMB session information that helps answer these questions.

---

# Investigation Objectives

- Understand SMB.
- Create a Windows SMB share.
- Enumerate available SMB shares.
- Check SMB server configuration.
- Identify active SMB sessions.
- Review open SMB files.

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


# Investigation Findings

The investigation confirmed successful SMB share creation and enumeration using PowerShell. SMB server configuration was successfully reviewed, and the lab demonstrated the commands used to investigate SMB sessions and open files. 

