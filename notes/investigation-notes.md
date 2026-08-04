# Investigation Notes

## Lab Summary

This investigation focused on understanding Windows SMB shares and introducing SMB session analysis using native Windows PowerShell.

The investigation demonstrated how shared folders are created, validated, and examined while introducing the commands used to investigate SMB sessions and server configuration.

---

## Analyst Methodology

1. Create investigation workspace.
2. Create sample files.
3. Create SMB share.
4. Validate share creation.
5. Access shared folder.
6. Enumerate SMB shares.
7. Review SMB sessions.
8. Review SMB open files.
9. Examine SMB server configuration.
10. Correlate findings.
11. Document evidence.

---

## Investigation Scenario

A Windows folder was shared to simulate a network file share.

The investigation aimed to determine:

- Which folders were shared.
- Whether SMB sessions were established.
- Whether files were opened through SMB.
- How PowerShell could enumerate SMB artifacts.
- How SMB configuration supports forensic investigations.

---

## Evidence Collected

### Evidence 1 – Investigation Workspace

Collected:

- SMBLab directory
- Sample files

Finding:

Established investigation baseline.

---

### Evidence 2 – SMB Share

Command Used

```powershell
New-SmbShare -Name DFIRShare -Path C:\SMBLab -FullAccess Everyone
```

Finding:

Successfully created a Windows SMB share.

---

### Evidence 3 – Share Enumeration

Command Used

```powershell
Get-SmbShare
```

Finding:

Verified the presence of DFIRShare.

---

### Evidence 4 – SMB Session Review

Command Used

```powershell
Get-SmbSession
```

Finding:

No active SMB session was observed during localhost testing. This behavior is expected on some Windows editions and local configurations.

---

### Evidence 5 – SMB Open Files

Command Used

```powershell
Get-SmbOpenFile
```

Finding:

No active SMB file handles were observed during local testing.

---

### Evidence 6 – SMB Server Configuration

Command Used

```powershell
Get-SmbServerConfiguration
```

Finding:

Reviewed Windows SMB protocol configuration, including SMBv2 support and server settings.

---

## DFIR Analysis

The investigation demonstrated how PowerShell can enumerate Windows SMB shares and server configuration while introducing the commands used to investigate active SMB sessions. Although localhost testing did not generate active session artifacts, the methodology remains identical to enterprise investigations where remote systems access shared resources.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Lateral Movement | SMB/Windows Admin Shares | T1021.002 |
| Collection | Data from Network Shared Drive | T1039 |

---

## Analyst Observations

- SMB shares can be created and managed entirely through PowerShell.
- Get-SmbShare provides reliable share enumeration.
- Localhost testing may not generate active SMB session artifacts.
- SMB server configuration offers valuable security information.
- Enterprise investigations typically reveal additional session evidence when remote clients connect.

---

## Conclusion

The investigation successfully demonstrated Windows SMB share creation, enumeration, and configuration analysis using native Windows PowerShell while introducing the methodology used to investigate SMB sessions and shared resource activity during DFIR investigations.
